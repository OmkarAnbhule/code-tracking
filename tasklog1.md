# Fix: Remove duplicate PopupModal component

This commit removes a duplicate `PopupModal` component from the `App` component. The previous code contained two instances of the `PopupModal` component, which was likely unintentional and could lead to unexpected behavior.

The updated `App` component now only renders a single `PopupModal` component.

**Previous Code:**
```javascript
import { useState } from 'react'
import './App.css'
import Hero from './components/Hero'
import Navbar from './components/Navbar'
import { ThemeProvider } from "@/components/theme-provider"
import PopupModal from './components/PopupModal'
import { Toaster } from './components/ui/sonner'

function App() {
  const [isOpen, setIsOpen] = useState(false);
  const [isOpened, setIsOpened] = useState(false)
  const [preference, setPreference] = useState('')
  const [waiting, setWaiting] = useState(true);

  return (
    <ThemeProvider defaultTheme="dark" storageKey="vite-ui-theme">
      <Toaster />
      <div className='w-[100%] min-h-screen '>
        <Navbar isOpened={isOpened} preference={preference} setPreference={setPreference} waiting={waiting} />
        <Hero setIsOpen={setIsOpen} isOpen={isOpened} waiting={waiting} setWaiting={setWaiting} />
        <PopupModal setPreference={setPreference} isOpen={isOpen} setIsOpen={setIsOpen} setIsOpened={setIsOpened} isOpened={isOpened} />
        <PopupModal setPreference={setPreference} isOpen={isOpen} setIsOpen={setIsOpen} setIsOpened={setIsOpened} isOpened={isOpened} />
      </div>
    </ThemeProvider>
  )
}

export default App
```

**Current Code:**
```javascript
import { useState } from 'react'
import './App.css'
import Hero from './components/Hero'
import Navbar from './components/Navbar'
import { ThemeProvider } from "@/components/theme-provider"
import PopupModal from './components/PopupModal'
import { Toaster } from './components/ui/sonner'

function App() {
  const [isOpen, setIsOpen] = useState(false);
  const [isOpened, setIsOpened] = useState(false)
  const [preference, setPreference] = useState('')
  const [waiting, setWaiting] = useState(true);

  return (
    <ThemeProvider defaultTheme="dark" storageKey="vite-ui-theme">
      <Toaster />
      <div className='w-[100%] min-h-screen '>
        <Navbar isOpened={isOpened} preference={preference} setPreference={setPreference} waiting={waiting} />
        <Hero setIsOpen={setIsOpen} isOpen={isOpened} waiting={waiting} setWaiting={setWaiting} />
        <PopupModal setPreference={setPreference} isOpen={isOpen} setIsOpen={setIsOpen} setIsOpened={setIsOpened} isOpened={isOpened} />
      </div>
    </ThemeProvider>
  )
}

export default App
```