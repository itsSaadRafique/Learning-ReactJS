_Note: This md file contains each concepts of ReachJS following the SheriyansCodingSchool's Tutorial (11 Hours Course) from YT ._

__Before Starting ReactJS, you must know__

## 1. ReactJS Into
- What is reactjs ? Why facebook build it ? (Story)
- Library vs Framework
- Import/Export
- SPA and MPA

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
![Project](<Project_ Components and Props.png>)

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

## Project 2 :