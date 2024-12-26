# Feature: Add Toaster Component

This commit introduces a `Toaster` component from the `./components/ui/sonner` module to the application.  The `Toaster` is rendered within the `ThemeProvider` to provide feedback to the user. No changes were made to the core application logic.

**Previous Code (for reference):**
The previous code was identical to the current code except for the absence of the `<Toaster />` component.

**Current Code:**
```jsx
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
      <div className='w-[100%] min-h-screen'>
        <Navbar isOpened={isOpened} preference={preference} setPreference={setPreference} waiting={waiting} />
        <Hero setIsOpen={setIsOpen} isOpen={isOpened} waiting={waiting} setWaiting={setWaiting} />
        <PopupModal setPreference={setPreference} isOpen={isOpen} setIsOpen={setIsOpen} setIsOpened={setIsOpened} isOpened={isOpened} />
        Hello World
      </div>
    </ThemeProvider>
  )
}

export default App
```