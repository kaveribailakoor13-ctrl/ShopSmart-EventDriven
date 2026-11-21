# 🛒 ShopSmart: Event-Driven Online Store Architecture

> **Build Bengaluru 2.0 // Round 2 // Online Store**  
> **Team:** Team Sinavi | **Team ID:** AFF7B51872EC  
> **Members:** Sai Sinchana • H Nandini • Kaveri Shivappa Bailakoor

---

## 🚀 About the Project
ShopSmart is a highly scalable, decoupled online store architecture designed to solve the common pitfalls of basic e-commerce platforms. By leveraging an event-driven design, we ensure ACID-compliant stock tracking, typo-tolerant product discovery, and non-blocking checkout experiences.

## 🎯 Problem Statement & Our Solution
| Existing Challenge | Our Engineering Goal | Primary Engine |
| :--- | :--- | :--- |
| **Overselling Stock** | ACID Storage for accurate product & stock records | **PostgreSQL** |
| **Rigid Search** | Fuzzy search to handle minor spelling typos | **OpenSearch** |
| **Slow Checkout** | Decouple order tasks (email, stock updates) asynchronously | **Apache Kafka** |
| **Tight Coupling** | Clean, decoupled stack so one failing service doesn't stall the store | **Python + JS** |

## 🛠️ Tech Stack
- **Frontend:** HTML, CSS, JavaScript (Clean, responsive UI)
- **Backend API:** Python (FastAPI/Flask)
- **Database (ACID):** PostgreSQL (Products, Carts, Orders, Stock)
- **Event Streaming:** Apache Kafka (Order placed & inventory events)
- **Search Engine:** OpenSearch (Typo-tolerant search & category filters)
- **Infrastructure:** Docker & Docker Compose

## 🏗️ System Architecture (Data Flow)
1. **User Action:** Customer searches for "wirless audio" on the Web UI.
2. **Search:** Python API queries **OpenSearch**, which handles the typo and returns "Wireless Audio" with filters.
3. **Cart & Checkout:** User adds to cart. Python API validates live stock availability via **PostgreSQL**.
4. **Async Event:** Upon "Place Order", the API publishes an `order-placed` event to **Apache Kafka** and instantly confirms the order to the user.
5. **Background Processing:** A **Kafka Consumer** picks up the event, deducts the inventory in PostgreSQL, and triggers order confirmation workflows without blocking the user.

## ✨ Key Features
- ✅ **Typo-Tolerant Discovery:** Finds misspelled items instantly with category filters.
- ✅ **Real-Time Stock Validation:** Prevents overselling during concurrent checkouts.
- ✅ **Non-Blocking Checkout:** Users get instant confirmation while background workers handle inventory and notifications.
- ✅ **Horizontal Scalability:** Add more Kafka consumers during flash sales without touching the database or search nodes.

## 🚀 Getting Started (Local Setup)
*Prerequisites: Docker & Docker Compose installed*

1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/ShopSmart.git
   cd ShopSmart

   https://1drv.ms/f/c/666e91df76557ea6/IgCdL4NDswgmRqREwog69hmnAbpCXxNVwwusvQVXwiAwkbA?e=IK2Dok
   
