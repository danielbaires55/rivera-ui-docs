---
title: Grid Component
description: Documentation for the Grid component in Rivera-UI.
sidebar_position: 3
---

# Grid Component

The `Grid` component is a flexible layout structure that displays key features in a responsive grid format. It utilizes Material-UI components and provides an elegant way to showcase information.

## ✨ Features
- Uses Material-UI components (`Box`, `Card`, `CardContent`, `Typography`, and `Stack`).
- Displays feature items dynamically using an array.
- Fully responsive layout with flex wrapping.
- Supports theme-based styling and customization.

## 📌 Usage

Import the `Grid` component and use it within your React application.

```tsx
import { Grid } from "@rivera-ui/grid";

function App() {
  return (
    <div>
      <Grid />
    </div>
  );
}

export default App;
```

## 🏗️ Code Implementation

```tsx
import { Box, Card, CardContent, Typography, Stack } from "@mui/material";
import styles from "./grid.module.css";

export function Grid() {
  const gridItems = [
    { title: "Design System", description: "Consistent UI components." },
    { title: "Dark Mode", description: "Built-in theme support." },
    { title: "Performance", description: "Optimized rendering speed." },
    { title: "Accessibility", description: "ARIA-compliant components." },
    { title: "Customization", description: "Fully extendable styles." },
    { title: "Open Source", description: "MIT-licensed and community-driven." },
  ];

  return (
    <Box className={styles.gridContainer}>
      <Stack
        direction="row"
        flexWrap="wrap"
        justifyContent="center"
        gap={4}
      >      
        {gridItems.map((item, index) => (
          <Card key={index} className={styles.gridItem}>
            <CardContent>
              <Typography variant="h5" component="h3">
                {item.title}
              </Typography>
              <Typography variant="body1" color="textSecondary">
                {item.description}
              </Typography>
            </CardContent>
          </Card>
        ))}
      </Stack>
    </Box>
  );
}

export default Grid;
```

## 🛠️ Props
The `Grid` component does not accept any props but can be customized by modifying the `gridItems` array or applying custom styles.

## 🎨 Customization
You can modify the styles using a CSS module or adjust Material-UI's theme.

For example, changing the spacing between items:

```tsx
<Stack direction="row" flexWrap="wrap" justifyContent="center" gap={2}>
```

## 🏁 Conclusion
The `Grid` component provides a structured way to showcase key features in a responsive layout. You can extend it with additional styles, animations, or interactivity as needed.

