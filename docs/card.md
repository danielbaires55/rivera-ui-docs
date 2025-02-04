---
title: PricingCard Component
description: Documentation for the PricingCard component in Rivera-UI.
sidebar_position: 4
---

# PricingCard Component

The `PricingCard` component is a modern and responsive pricing card built using Material-UI. It features an expandable section to display additional pricing details.

## ✨ Features
- Uses Material-UI components (`Card`, `CardHeader`, `CardContent`, `CardActions`, `Collapse`, `Avatar`, `Typography`, and `Button`).
- Displays **pricing details** in an elegant and structured manner.
- Includes an **expandable section** for additional information.
- Styled with **Material-UI's theme** for seamless integration.

## 📌 Usage

Import the `PricingCard` component and use it within your React application.

```tsx
import { PricingCard } from "@rivera-ui/pricing-card";

function App() {
  return (
    <div>
      <PricingCard />
    </div>
  );
}

export default App;
```

## 🏗️ Code Implementation

```tsx
import * as React from "react";
import Card from "@mui/material/Card";
import CardHeader from "@mui/material/CardHeader";
import CardContent from "@mui/material/CardContent";
import CardActions from "@mui/material/CardActions";
import Collapse from "@mui/material/Collapse";
import Avatar from "@mui/material/Avatar";
import IconButton from "@mui/material/IconButton";
import Typography from "@mui/material/Typography";
import { red } from "@mui/material/colors";
import ExpandMoreIcon from "@mui/icons-material/ExpandMore";
import MoreVertIcon from "@mui/icons-material/MoreVert";
import Box from "@mui/material/Box";
import Button from "@mui/material/Button";

export const PricingCard: React.FC = () => {
  const [expanded, setExpanded] = React.useState(false);

  const handleExpandClick = () => {
    setExpanded(!expanded);
  };

  return (
    <Box sx={{ display: "flex", justifyContent: "center", alignItems: "center", height: "100vh", mt: 1 }}>
      <Card sx={{ maxWidth: 500, width: "100%", p: 3, borderRadius: 3, boxShadow: 5 }}>
        {/* Header */}
        <CardHeader
          avatar={<Avatar sx={{ bgcolor: red[500] }} aria-label="plan">P</Avatar>}
          action={<IconButton aria-label="settings"><MoreVertIcon /></IconButton>}
          title={<Typography variant="h5" fontWeight="bold">Basic Plan</Typography>}
          subheader="Perfect for small teams"
        />

        {/* Pricing Information */}
        <CardContent>
          <Typography variant="h4" fontWeight="bold" color="primary">$19.99</Typography>
          <Typography variant="body1" color="textSecondary">/month</Typography>
        </CardContent>

        {/* Features List */}
        <CardContent>
          <Typography variant="body1">✅ 1 User License</Typography>
          <Typography variant="body1">✅ 5GB Cloud Storage</Typography>
          <Typography variant="body1">✅ Basic Support</Typography>
        </CardContent>

        {/* Call to Action */}
        <CardActions sx={{ justifyContent: "space-between" }}>
          <Button variant="contained" color="primary" fullWidth>Choose Plan</Button>
        </CardActions>

        {/* Expandable Details */}
        <CardActions disableSpacing>
          <IconButton onClick={handleExpandClick} aria-expanded={expanded} aria-label="show more">
            <ExpandMoreIcon sx={{ transform: expanded ? "rotate(180deg)" : "rotate(0deg)" }} />
          </IconButton>
        </CardActions>

        {/* Collapsible Details */}
        <Collapse in={expanded} timeout="auto" unmountOnExit>
          <CardContent>
            <Typography>Upgrade to our Premium Plan for:</Typography>
            <Typography variant="body1">⭐ 10 User License</Typography>
            <Typography variant="body1">⭐ 50GB Cloud Storage</Typography>
            <Typography variant="body1">⭐ 24/7 Premium Support</Typography>
          </CardContent>
        </Collapse>
      </Card>
    </Box>
  );
};

export default PricingCard;
```

## 🛠️ Props
The `PricingCard` component does not accept any props but can be customized by modifying its styles, pricing details, and features.

## 🎨 Customization

You can modify the styles using Material-UI's `sx` prop or by overriding styles in a separate CSS file.

For example, changing the card's background color:

```tsx
<Card sx={{ backgroundColor: "#f5f5f5" }}>
```

## 🏁 Conclusion

The `PricingCard` component provides a clean and structured way to display pricing information in your application. You can expand it by adding more plans, integrating it with a payment system, or customizing its appearance.

