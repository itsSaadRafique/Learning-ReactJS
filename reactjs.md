_Note: This md file contains each concepts of ReachJS following the SheriyansCodingSchool's Tutorial (11 Hours Course) from YT ._

__Before Starting ReactJS, you must know__

## 1. ReactJS Into
- What is reactjs ? Why facebook build it ? (Story)
- Library vs Framework
- Import/Export
- SPA and MPA

#
## 2. Create React Folder with Vite
To create a reactjs folder (with pre-build all necessary files and folders) , you need to open the terminal in the desired location you want to make a folder. 

If you already install the __NodeJS Application__ then type these commands in the teminal.

```bash 
npm create vite
```
- Name your folder 
- Select framework -> __React__


__Now__ open the terminal in the folder you made and run these commands.

```bash 
cd folder-you-made
npm install
npm run dev
````

Your reactjs folder is created successfully have all necessary files and folders .

#
## 5. Components
Component is like a function that does specific task.

__Code__  
- App.jsx
```bash
// Component 1
export default function Hero() {
  return <div className="hero">
    <h2>Hero Section</h2>
  </div>
}

// Component 2
export function Nav() {
  return <div className="nav">
    <h2>Navbar Section</h2>
  </div>
}

// Component 3
export function Footer() {
  return <div className="footer">
    <h2>Footer</h2>
  </div>
}
```

- main.jsx
```bash
import { createRoot } from 'react-dom/client'
import './index.css'
import Hero, { Nav, Footer } from './App.jsx'

createRoot(document.getElementById('root')).render(
  <>
    <Nav />
    <Hero />
    <Footer />
  </>
)
```

_Efficient way of using components is to making a separate folder that has all the separate components/funstions_

#
## 6. Props  
Adding desired data using same function.  
Its like passing values in functions and using them.


Let us consider a card havind username and age.  
- card.jsx
```bash
import React from 'react'

// Catching values as 'props' parameter
const Card = (props) => { 
  return (
    <div className='card'>
        {props.username} {props.age}
    </div>
  )
}

export default Card
```

- App.jsx
```bash
import Card from '../components/card.jsx'

const App = () => {
  return (
    <>
      // Here we pass desired values 
      <Card username="Bilal" age={10} />
      <Card username="Ali" age={49} />
      <Card username="Hamza" age={21} />
    </>
  )
}

export default App
```

## Project : Components and Props  
Make instagram profie like cards ( having profile pic, name , info and profile-view button) as shown in given picture.

__ScreenShot__ 
![Project](<./assets/Project_ Components and Props.png>)

__Code__
- card.jsx
```bash
import React from 'react'

const Card = (props) => {
  return (
    <div className="card">
      <img src={props.img} />
      <h2>{props.name}</h2>
      <p>Lorem ipsum dolor sit amet consectetur.</p>
      <button>View Profile</button>
    </div>
  )
}

export default Card
```

- App.jsx 
```bash
import Card from "../components/card.jsx";

const  App = () => {
  return (
    <>
      <Card name="Saad" img = "https://images.unsplash.com/photo-1529665253569-6d01c0eaf7b6?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8cHJvZmlsZXxlbnwwfHwwfHx8MA%3D%3D"/>

      <Card name="Haider" img = "https://images.unsplash.com/photo-1492562080023-ab3db95bfbce?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NTV8fHByb2ZpbGV8ZW58MHx8MHx8fDA%3D"/>

      <Card name="Waqas" img = "https://images.unsplash.com/photo-1527980965255-d3b416303d12?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NjR8fHByb2ZpbGV8ZW58MHx8MHx8fDA%3D"/>

    </>
  )
}

export default App
```

#
# 7. Simple CSS
We followed the method in which all of the css styles contain in only one globla style.css file .  
Which results  
- same classname elements catches the same css   
i.e __ all button having same classname (btn) catches the same styles from the global css file.

### But   
If we want all of the buttons having same name (btn) but catches the desired css styles , then we will use the concept of __MODULE CSS__ .
 
# Module CSS
In module css , we will write css in different .css files for each component.  
So this way , all of the buttons having same classname (btn) in each .css file but different styles for each button.

- example
![Project](<./assets/module css.png>)

_here button 1 and button 2 have same name (btn) in their own css file but different in styles because of their own .css files reference_

__CSS Code__
- header.module.css 
```bash
.header {
    width: 300px;
    padding: 10px;
    background-color: black;

    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;
}


/* this is for button 1  */
.btn {
    background-color: rgb(239, 70, 14);
    color: white;
    padding: 5px 10px;
    border-radius: 5px;
}
```


- button.module.css
```bash
/* this if for button 2  */
.btn {
    padding: 10px 20px;
    background-color: rgb(124, 31, 206);
    border-radius: 10px;
    margin-left: 10px;
}
```

__.jsx Code__
- header.jsx
```bash
import React from 'react'
import styles from './header.module.css'


const header = () => {
  return (
    <div className={styles.header}>
      <h2>This is header</h2>
      <button className={styles.btn}>Button 1</button>

    </div>
  )
}

export default header
```
-button.jsx
```bash
import React from 'react'
import styles from './button.module.css'

const button = () => {
  return (
    <button className={styles.btn} >Button 2</button>
  )
}

export default button

``` 
in both .jsx files , the classname of button {styles.btn} = btn , which is refering to their own .css file.

__Summary__  
.css files are separated , so the styles will be different.

