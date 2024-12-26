# Feature: Add Toaster Component

This commit introduces a `Toaster` component from `./components/ui/sonner`  to the `App` component.  The `Toaster` component is rendered twice. The purpose of this addition is likely for displaying notifications or messages to the user.

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
      <Toaster/>
      <Toaster/>
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