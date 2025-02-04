---
title: Header Component
description: Documentation for the Header component in Rivera-UI.
sidebar_position: 1
---

# Header Component

The `Header` component is a responsive navigation bar built using Material-UI. It provides a simple structure with a logo, a menu button, and an action button.

## ✨ Features
- Uses Material-UI components (`AppBar`, `Toolbar`, `IconButton`, `Typography`, and `Button`).
- Includes a **menu button** (`MenuIcon`) for navigation.
- Displays a **logo and title** (`Rivera-UI` with an icon).
- Contains a **login button** for user authentication actions.

## 📌 Usage

Import the `Header` component and use it within your React application.

```tsx
import { Header } from "@rivera-ui/header";

function App() {
  return (
    <div>
      <Header />
    </div>
  );
}

export default App;
```

## 🏗️ Code Implementation

```tsx
import AppBar from '@mui/material/AppBar';
import Box from '@mui/material/Box';
import Toolbar from '@mui/material/Toolbar';
import Typography from '@mui/material/Typography';
import Button from '@mui/material/Button';
import IconButton from '@mui/material/IconButton';
import MenuIcon from '@mui/icons-material/Menu';
import { GiAbstract070 } from "react-icons/gi";

export function Header() {
  return (
    <Box sx={{ flexGrow: 1 }}>
      <AppBar position="static">
        <Toolbar>
          <IconButton
            size="large"
            edge="start"
            color="inherit"
            aria-label="menu"
            sx={{ mr: 2 }}
          >
            <MenuIcon />
          </IconButton>
          <Typography variant="h6" component="div" sx={{ flexGrow: 1 }}>
            Rivera-Ui <GiAbstract070 />
          </Typography>         
          <Button color="inherit">Login</Button>
        </Toolbar>
      </AppBar>
    </Box>
  );
}

export default Header;
```

## 🛠️ Props
The `Header` component does not accept any props but can be customized by modifying the internal components such as the title, icons, and buttons.

## 🎨 Customization

You can modify the styles using Material-UI's `sx` prop or by overriding styles in a separate CSS file.

For example, changing the background color:

```tsx
<AppBar position="static" sx={{ backgroundColor: "#1976d2" }}>
```

## 🏁 Conclusion

The `Header` component provides a structured and customizable navigation bar for your application. You can expand it by adding more menu options, dropdowns, or additional action buttons.