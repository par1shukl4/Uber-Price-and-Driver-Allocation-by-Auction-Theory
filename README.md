# Market Dynamics Simulator: Game-Theoretic Ride-Hailing Platform

### Developed by: Pari Shukla
**NSUT Engineering | pari.shukla.ug23@nsut.ac.in**

---

## Project Overview
The Market Dynamics Simulator is a high-fidelity React-based simulation designed to demonstrate the application of Behavioral Economics and Algorithmic Game Theory in modern logistics. Inspired by the Uber ecosystem, this platform explores the tension between supply-demand volatility, truthful pricing mechanisms, and strategic driver coordination.

This project specifically implements the Vickrey-Clarke-Groves (VCG) auction model for price discovery and Nash Equilibrium frameworks for optimal driver-to-rider allocation.

---

## Core Scientific Frameworks

### 1. Truthful Pricing: The Vickrey Auction
In standard markets, bidders often engage in "shill bidding" or strategic overpricing to maximize margins. To combat this, this simulator utilizes a Second-Price Sealed-Bid Auction (Vickrey Auction).

* **Mechanism:** When a user requests a ride, the platform generates N competitive bids from available drivers.
* **The Winner:** The driver with the lowest bid wins the right to provide the service.
* **The Payment:** The user pays the price of the second-lowest bid.
* **Scientific Rationale:** This mechanism ensures that "Truth-telling" is a Dominant Strategy. Drivers are incentivized to bid their true operational cost, as bidding higher risks losing the job, while bidding lower does not affect their actual payout.

### 2. Strategic Allocation: Normal Form Games
The driver assignment phase is modeled as a Simultaneous Move Game between rational actors. We analyze driver behavior through a 2x2 Payoff Matrix (Normal Form).

| Driver A \ Driver B | Accept Ride | Reject (Wait for Surge) |
| :--- | :--- | :--- |
| **Accept Ride** | **(10, 10)** | (15, 0) |
| **Reject** | (0, 15) | (0, 0) |

* **Nash Equilibrium:** The state (Accept, Accept) represents the Nash Equilibrium in a coordination game. Neither driver can improve their utility by unilaterally changing their strategy, ensuring system stability and high fulfillment rates.

### 3. Dynamic Scarcity and Utility Scoring
The Final Match is determined by a Multi-Attribute Utility Function (MAUF), weighting three critical dimensions:

$$Score = 0.5 \times (1/ETA) + 0.3 \times (Rating) + 0.2 \times (Incentive)$$

* **Locational Scarcity:** The engine implements a 1.6x multiplier for high-intensity zones (Airports/Hospitals).
* **Temporal Surge:** Real-time system clock analysis applies multipliers of 1.3x to 1.5x during peak demand windows.

---

## Technical Implementation

### Tech Stack
* **Library:** React 18 (Client-side rendering)
* **Styling:** Tailwind CSS (Uber-Modern Aesthetic)
* **Animations:** CSS3 Transitions and Keyframes
* **Icons:** Lucide-React

### Key Features
* **Real-Time Price Discovery:** Auction bids shift instantly as demand and supply sliders are adjusted.
* **Dynamic Logic Engine:** Automatic detection of peak hours and location-based priority pricing.
* **Interactive Science Deck:** Embedded academic explanations for the economic mechanisms utilized.
* **Mobile-First UX:** Structured within a custom-built smartphone frame with fixed-header/scrollable-body architecture.

---

## Installation and Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/parishukla/market-dynamics-simulator.git](https://github.com/parishukla/market-dynamics-simulator.git)
