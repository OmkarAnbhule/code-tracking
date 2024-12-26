# Feature: Add Toaster for Notifications

This commit introduces a `Toaster` component from `./components/ui/sonner` to the application.  The `Toaster` is now rendered within the `ThemeProvider` to provide visual notifications to the user.

No changes were made to the core functionality or structure of the application itself. The `Toaster` component simply enhances the user experience by providing a method for displaying notifications.

**Previous Code (No changes):**
```javascript
import { useState } from 'react'
import './App.css'
import Hero from './components/Hero'
import Navbar from './components/Navbar'
import { ThemeProvider } from "@/components/theme-provider"
import PopupModal from './components/PopupModal'

function App() {
  const [isOpen, setIsOpen] = useState(false);
  const [isOpened, setIsOpened] = useState(false)
  const [preference, setPreference] = useState('')
  const [waiting, setWaiting] = useState(true);

  return (
    <ThemeProvider defaultTheme="dark" storageKey="vite-ui-theme">
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