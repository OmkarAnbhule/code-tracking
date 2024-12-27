# Feature: Add a simple message to the App component

This commit introduces a simple message, "Hello world this is new Commit", to the main App component.  This message is rendered within a div element and serves as a placeholder or test message for development purposes. 

No changes were made to the overall structure or functionality of the application. The existing components (Navbar, Hero, PopupModal, and Toaster) remain unchanged.  The updated code is below:

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
      <div className='w-[100%] min-h-screen '>
        <Navbar isOpened={isOpened} preference={preference} setPreference={setPreference} waiting={waiting} />
        <Hero setIsOpen={setIsOpen} isOpen={isOpened} waiting={waiting} setWaiting={setWaiting} />
        <PopupModal setPreference={setPreference} isOpen={isOpen} setIsOpen={setIsOpen} setIsOpened={setIsOpened} isOpened={isOpened} />
        <div>
          Hello world this is new Commit
        </div>
      </div>
    </ThemeProvider>
  )
}

export default App
```

The previous code was identical to the current code except for the addition of this message.  Therefore, no specific comparison is needed beyond noting the addition of the new message.
