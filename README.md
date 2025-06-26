# ServiceTitan_Task

## Customer Data Extractor

This project extracts, transforms, and flattens nested customer order data from a `.pkl` file and combines it with a VIP customer list from a `.txt` file. The final output is a clean and analysis-ready `.csv` file.

## Features

- Parses nested customer order data from a pickle file.
- Converts and cleans data into a flat tabular format.
- Handles missing values and type inconsistencies.
- Recovers missing `order_id`, `product_id`, and `product_name` from patterns in product descriptions.
- Maps product category codes to human-readable names.
- Exports the cleaned dataset as a `.csv` file.

## File Structure

- `customer_orders.pkl` — Pickle file containing a list of customer records with nested orders and items.
- `vip_customers.txt` — Text file containing a list of VIP customer IDs (one per line).
- `cleaned_output.csv` — Flattened and cleaned output file.

## Output Columns and Data Types

| Column                      | Data Type        | Description                                      |
|----------------------------|------------------|--------------------------------------------------|
| `customer_id`              | Int64            | Customer ID                                      |
| `customer_name`            | str (object)     | Name of the customer                             |
| `registration_date`        | datetime64[ns]   | Registration date (date & time)                    |
| `is_vip`                   | bool             | True if customer is a VIP                        |
| `order_id`                 | Int64            | Order ID                                         |
| `order_date`               | datetime64[ns]   | Order date (date & time)                           |
| `product_id`               | Int64            | Product/item ID                                  |
| `product_name`             | str (object)     | Product name (e.g., "Item 1 for Order 2")        |
| `category`                 | str (object)     | Product category ("Electronics", "Apparel", etc.)|
| `unit_price`               | float            | Price per item                                   |
| `item_quantity`            | int              | Number of items                                  |
| `total_item_price`         | float            | Total price for that item                        |
| `total_order_value_percentage` | float       | Percentage of item cost in total order           |

## Usage

```bash
python task.ipynb
```

## Requirements
Python 3.6+

pandas

## Author
Lili Kostanyan
