---
title: Hero Component
description: Documentation for the Hero component in Rivera-UI.
sidebar_position: 2
---

# Hero Component

The `Hero` component is a visually appealing introduction section designed for landing pages.  
It features a **title**, **subtitle**, and **call-to-action buttons** to guide users.

## ✨ Features
- Displays a **title** and **subtitle** to introduce the application.
- Includes two **call-to-action buttons** for user engagement.
- Uses **CSS Modules** for styling.
- Supports an optional `onComponentsClick` callback for navigation.

## 📌 Usage

Import the `Hero` component and use it within your React application.

```tsx
import { Hero } from "@rivera-ui/hero";

function App() {
  return (
    <div>
      <Hero onComponentsClick={() => console.log("Navigate to components section")} />
    </div>
  );
}

export default App;
```

## 🏧 Code Implementation

```tsx
import styles from './hero.module.css';

interface HeroProps {
  onComponentsClick?: () => void;
}

export function Hero({ onComponentsClick }: HeroProps) {
  return (
    <div className={styles.heroContainer}>
      <div className={styles.heroContent}>
        <h1 className={styles.heroTitle}>App Library</h1>
        <p className={styles.heroSubtitle}>
          A free, modern, and minimalist React UI library.
          (This is the Hero component).
        </p>
        <div className={styles.heroCta}>
          <button className={styles.ctaPrimary}>Get Started</button>
          <button className={styles.ctaSecondary} onClick={onComponentsClick}>
            Components
          </button>
        </div>
      </div>
    </div>
  );
}

export default Hero;
```

## 🛠️ Props

The `Hero` component accepts the following props:

| Name                | Type         | Default     | Description |
|---------------------|-------------|-------------|-------------|
| `onComponentsClick` | `() => void` | `undefined` | Callback function triggered when the "Components" button is clicked. |

## 🎨 Customization

The component uses **CSS Modules** for styling. You can modify `hero.module.css` to change the appearance.  

For example, changing the background color:

```css
.heroContainer {
  background-color: #f5f5f5;
  padding: 4rem 2rem;
}
```

## 🏁 Conclusion

The `Hero` component provides a stylish introduction section for your application.  
It can be expanded with animations, additional buttons, or different layouts to fit your design needs.

