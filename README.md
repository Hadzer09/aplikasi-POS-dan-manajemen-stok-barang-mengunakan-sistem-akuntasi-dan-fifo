# POS & Inventory System with Accounting (FIFO)

A web-based Point of Sales (POS) application with inventory management and built-in accounting, designed for small and medium enterprises (SMEs). Sales transactions automatically update stock and generate journal entries, and inventory is valued using the **FIFO (First-In, First-Out)** method.

Built as a final-year project for the Associate Degree in Accounting Information Systems at Telkom University.

## Features

- **Point of Sales**: record sales transactions quickly.
- **Inventory management**: track products and stock levels.
- **FIFO inventory costing**: the oldest stock is sold first, so the cost of goods sold follows the purchase cost of the oldest stock.
- **Automated journal entries**: transactions are recorded as accounting journals without manual input.
- **Financial documentation**: transaction and accounting records are kept in one system.
- **Responsive UI**: works on desktop and mobile screens.

<!-- TODO: add or remove features so this list matches your app (e.g. user roles, purchase module, reports, receipt printing). -->

## Tech Stack

| Layer | Technology |
| --- | --- |
| Backend | PHP, Laravel (MVC) |
| Database | MySQL |
| Frontend | Blade, Tailwind CSS |
| Build tool | Vite |

## Screenshots

<!-- TODO: add 3-4 screenshots (login, POS/cashier page, stock page, journal/report page). -->
<!-- Example: ![POS page](docs/screenshots/pos.png) -->

## Getting Started

### Requirements

- PHP and Composer (see `composer.json` for the required PHP version)
- Node.js and npm
- MySQL

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Hadzer09/aplikasi-POS-dan-manajemen-stok-barang-mengunakan-sistem-akuntasi-dan-fifo.git
cd aplikasi-POS-dan-manajemen-stok-barang-mengunakan-sistem-akuntasi-dan-fifo

# 2. Install PHP and JavaScript dependencies
composer install
npm install

# 3. Set up the environment file
cp .env.example .env
php artisan key:generate
```

Create an empty MySQL database, then update the database settings in `.env`:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_database_name
DB_USERNAME=root
DB_PASSWORD=
```

```bash
# 4. Create the database tables
php artisan migrate

# 5. Run the app (use two terminals)
npm run dev
php artisan serve
```

Open http://127.0.0.1:8000 in your browser.

<!-- TODO: if the project has seeders, add `php artisan db:seed` after migrate and list the default login below. -->
<!-- TODO: if the `tokodistro2` file in the root is a database dump, explain how to import it here. -->

## Default Login

<!-- TODO: fill in or delete this section. -->

| Role | Email | Password |
| --- | --- | --- |
| Admin | _to be added_ | _to be added_ |

## How FIFO Works in This App

When stock is bought in several batches at different prices, FIFO assumes the oldest batch is sold first. For example:

| Purchase | Quantity | Unit cost |
| --- | --- | --- |
| Batch 1 | 10 | Rp 50.000 |
| Batch 2 | 10 | Rp 55.000 |

Selling 12 units uses all 10 units from Batch 1 and 2 units from Batch 2, so the cost of goods sold is (10 × 50.000) + (2 × 55.000) = Rp 610.000. That cost is what goes into the journal entry for the sale.

Author

Hafidz Muyassar – Junior Web Developer
GitHub: [@Hadzer09](https://github.com/Hadzer09)
