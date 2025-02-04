---
title: Footer Component
description: Documentation for the Footer component in Rivera-UI.
sidebar_position: 5
---

# Footer Component

The `Footer` component is a fixed footer bar for displaying copyright information and important links.

## ✨ Features
- Uses Material-UI components (`Box`, `Typography`, and `Link`).
- **Fixed position** at the bottom of the page.
- **Customizable background color** and padding.
- **Includes links** for Privacy Policy and Terms of Service.

## 📌 Usage

Import the `Footer` component and use it within your React application.

```tsx
import { Footer } from "@rivera-ui/footer";

function App() {
  return (
    <div>
      <Footer />
    </div>
  );
}

export default App;
```

## 🏗️ Code Implementation

```tsx
import * as React from 'react';
import { Box, Typography, Link } from '@mui/material';

export const Footer: React.FC = () => {
  return (
    <Box
      sx={{
        display: 'flex',
        justifyContent: 'center',
        alignItems: 'center',
        position: 'fixed',
        bottom: 0,
        width: '100%',
        backgroundColor: '#1976d2',
        padding: '16px 0',
      }}
    >
      <Typography variant="body2" color="white">
        &copy; {new Date().getFullYear()} Rivera-Ui. All rights reserved.
        <Link href="#" sx={{ color: 'white', textDecoration: 'none', marginLeft: 1 }}>
          Privacy Policy
        </Link> |
        <Link href="#" sx={{ color: 'white', textDecoration: 'none', marginLeft: 1 }}>
          Terms of Service
        </Link>
      </Typography>
    </Box>
  );
};

export default Footer;
```

## 🛠️ Props
The `Footer` component does not accept any props but can be customized using styles or additional elements.

## 🎨 Customization
You can modify the styles using Material-UI's `sx` prop.

For example, changing the background color:

```tsx
<Box sx={{ backgroundColor: "#333" }}>
```

## 🏁 Conclusion

The `Footer` component provides a simple and effective way to display legal information and links. You can extend it by adding social media icons or additional navigation links.

