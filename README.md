# E-commerce-Database-Design

Core Product Structure
product 🧾: The base unit, storing general info like name, brand, and base price.

brand 🏷️: Brands linked to products via foreign key.

product_category 📦: Classifies products into categories like "Clothing", "Electronics".

product_image 🎨: Stores multiple image URLs or paths per product (many-to-one).

Product Variations
product_item 🏷️: Each physical, purchasable item. Think: "T-shirt, Red, M".

product_variation 🔄: Links product_item to different combinations of options (color, size, etc.).

color 🗂️: Standardized list of colors.

size_category 📏: e.g., "Shoe Sizes", "Clothing Sizes".

size_option 📐: e.g., "S", "M", "42", associated with a size_category.

Product Attributes
product_attribute 🧵: Custom info like material, weight, power consumption, etc.

attribute_category 📚: Groups attributes—like "Physical Attributes", "Tech Specs".

attribute_type 🧪: Defines value types: string, number, boolean, etc

Notes
The product_attribute table supports multiple value types using value_text, value_number, and value_boolean. Only one should be used per attribute.

SKU is stored at the product_item level, representing a unique variation ready to sell.

product_variation links each SKU to its size and color.

Stock Keeping Unit (SKU)
A SKU is a unique identifier for each individual item that you can actually sell. It tracks specific variations like:

Product: T-shirt

Color: Red

Size: Medium

➡️ Together, this combo is one sellable SKU, often stored in a table like product_item.

🧠 Why It Matters:
It's what's in your inventory.

It's what customers add to their cart.

It's what gets shipped.

So while a product (like a T-shirt) is a general concept, a sellable SKU (T-shirt, red, M) is a specific version of that product that your system tracks for stock, pricing, and orders.
