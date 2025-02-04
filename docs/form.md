---
title: Form Component
description: Documentation for the Form component in Rivera-UI.
sidebar_position: 5
---

# Form Component

The `Form` component is a simple and user-friendly sign-up form built using Material-UI. It includes fields for name, email, and password, with built-in validation.

## ✨ Features
- Uses Material-UI components (`Box`, `TextField`, `Button`, and `Typography`).
- Includes **form validation** to ensure required fields are filled.
- Displays **error messages** for empty fields.
- Submits data and logs it to the console.

## 📌 Usage

Import the `Form` component and use it within your React application.

```tsx
import { Form } from "@rivera-ui/form";

function App() {
  return (
    <div>
      <Form />
    </div>
  );
}

export default App;
```

## 🏗️ Code Implementation

```tsx
import React, { useState } from "react";
import { Box, TextField, Button, Typography } from "@mui/material";

export const Form: React.FC = () => {
  const [formData, setFormData] = useState({
    name: "",
    email: "",
    password: "",
  });

  const [errors, setErrors] = useState({
    name: false,
    email: false,
    password: false,
  });

  const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
    setErrors({ ...errors, [e.target.name]: false });
  };

  const handleSubmit = (e: React.FormEvent) => {
    e.preventDefault();
    const newErrors = {
      name: formData.name === "",
      email: formData.email === "",
      password: formData.password === "",
    };

    setErrors(newErrors);

    if (!newErrors.name && !newErrors.email && !newErrors.password) {
      console.log("Form Submitted", formData);
      alert("Form Submitted Successfully!");
    }
  };

  return (
    <Box
      component="form"
      onSubmit={handleSubmit}
      sx={{
        maxWidth: 400,
        mx: "auto",
        mt: 2,
        mb: 5,
        p: 3,
        borderRadius: 2,
        boxShadow: 3,
        bgcolor: "background.paper",
      }}
    >
      <Typography variant="h5" textAlign="center" mb={2}>
        Sign Up
      </Typography>
      <TextField
        fullWidth
        label="Name"
        name="name"
        value={formData.name}
        onChange={handleChange}
        error={errors.name}
        helperText={errors.name ? "Name is required" : ""}
        sx={{ mb: 2 }}
      />
      <TextField
        fullWidth
        label="Email"
        name="email"
        type="email"
        value={formData.email}
        onChange={handleChange}
        error={errors.email}
        helperText={errors.email ? "Email is required" : ""}
        sx={{ mb: 2 }}
      />
      <TextField
        fullWidth
        label="Password"
        name="password"
        type="password"
        value={formData.password}
        onChange={handleChange}
        error={errors.password}
        helperText={errors.password ? "Password is required" : ""}
        sx={{ mb: 2 }}
      />
      <Button type="submit" variant="contained" fullWidth>
        Submit
      </Button>
    </Box>
  );
};

export default Form;
```

## 🛠️ Props
The `Form` component does not accept any props but can be customized by modifying the Material-UI styles and form fields.

## 🎨 Customization

You can customize the form's appearance by modifying the `sx` prop. For example, changing the background color:

```tsx
<Box sx={{ bgcolor: "#f5f5f5" }}>
```

## 🏁 Conclusion
The `Form` component provides a simple and clean user registration form with built-in validation. You can extend it by adding more fields, validation rules, or integrating it with a backend API.

