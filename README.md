# FakeStore

A modern e-commerce web application built with **React** and **TypeScript**, powered by the [FakeStore API](https://fakestoreapi.com). Browse products, explore categories, and experience a fully functional shopping interface.

---

## Features

- Browse products fetched from the FakeStore API
- Filter products by category
- Add items to a shopping cart
- Responsive design for mobile and desktop
- Built with TypeScript for type safety

---

## Tech Stack

| Technology | Purpose |
|---|---|
| React | UI library |
| TypeScript | Type-safe JavaScript |
| Redux Toolkit | Global state management |
| React-Redux | React bindings for Redux |
| i18next | Internationalization framework |
| react-i18next | React integration for i18next |
| FakeStore API | Product data source |
| Create React App | Project scaffolding |

---

## State Management — Redux
 
This project uses **Redux Toolkit** for global state management, keeping the cart, product list, and UI state predictable and easy to debug.
 
### Store Structure
 
```
src/
└── store/
    ├── index.ts          # Store configuration
    └── slices/
        ├── cartSlice.ts      # Cart items, quantities, totals
        └── productsSlice.ts  # Product list, loading, filters
```
 
### Key Slices
 
**Cart Slice** manages adding, removing, and updating items:
 
```ts
// Add item to cart
dispatch(addToCart(product));
 
// Remove item from cart
dispatch(removeFromCart(productId));
 
// Clear the entire cart
dispatch(clearCart());
```
 
**Products Slice** manages fetching and filtering:
 
```ts
// Fetch all products
dispatch(fetchProducts());
 
// Filter by category
dispatch(setCategory('electronics'));
```
 
### Accessing State
 
```ts
const cartItems = useSelector((state: RootState) => state.cart.items);
const products = useSelector((state: RootState) => state.products.items);
```

---

## 🌍 Internationalization — i18n
 
This project uses **i18next** with **react-i18next** to support multiple languages out of the box.
 
### Supported Languages
 
| Code | Language |
|---|---|
| `en` | English |
| `ru` | Russian |
| `kk` | Kazakh |

---

## Project Structure

```
FakeStore/
├── public/           # Static assets
├── src/              # Application source code
│   ├── components/   # Reusable UI components
│   ├── pages/        # Page-level components
│   ├── store/        # Redux store and slices
│   │   ├── index.ts
│   │   └── slices/
│   │       ├── cartSlice.ts
│   │       └── productsSlice.ts
│   ├── locales/      # i18n translation files
│   │   ├── en/translation.json
│   │   ├── ru/translation.json
│   │   └── kk/translation.json
│   ├── types/        # TypeScript type definitions
│   ├── App.tsx       # Root component
│   └── index.tsx     # Entry point
├── package.json
├── tsconfig.json
└── README.md
```

---

## Getting Started
### Installation

```bash
# Clone the repository
git clone https://github.com/ErnarM04/FakeStore.git

# Navigate into the project directory
cd FakeStore

# Install dependencies
npm install
```

### Running the App

```bash
# Start the development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to view the app.

### Building for Production

```bash
npm run build
```

The optimized production build will be output to the `build/` folder.

---

## API Reference

This project uses it's own public REST API for e-commerce prototyping.

| Endpoint | Description |
|---|---|
| `GET /products` | Fetch all products |
| `GET /products/:id` | Fetch a single product |
| `GET /products/categories` | Fetch all categories |
| `GET /products/category/:name` | Fetch products by category |

---

## Available Scripts

| Script | Description |
|---|---|
| `npm start` | Run the app in development mode |
| `npm test` | Launch the test runner |
| `npm run build` | Build the app for production |
| `npm run eject` | Eject from Create React App (irreversible) |

> Built by [ErnarM04](https://github.com/ErnarM04)
