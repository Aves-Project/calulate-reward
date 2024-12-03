### README for Aves Reward API

---

#### **Overview**
This Flask-based API provides the current block reward details for the Aves blockchain network. It dynamically calculates the miner's reward (95%) and the green fund's share (5%) based on the current block height and halving rules. The API is designed for mining pools to display accurate and up-to-date reward information in their UI.

---

#### **Features**
- Automatically fetches the current block number from the Aves blockchain.
- Calculates total block rewards with halving progression.
- Splits the reward into miner and green fund shares.
- Provides the reward values in both **AVS** (human-readable) and **Wei** (raw blockchain values).

---

#### **Prerequisites**
1. **Python**: Version 3.7 or higher.
2. **Dependencies**:
   Install the required Python packages:
   ```bash
   pip install Flask web3
   ```

---

#### **Configuration**
- Update the RPC URL in the script if necessary:
  ```python
  geth_rpc_url = "https://rpc.avescoin.io"
  ```

---

#### **Running the API**
1. Save the script as `reward_api.py`.
2. Start the Flask server:
   ```bash
   python reward_api.py
   ```
3. The API will run on `http://0.0.0.0:5000`.

---

#### **API Endpoint**

##### **GET /current-reward**
Fetch the current block reward details.

- **Response Example**:
  ```json
  {
    "block_number": 4872573,
    "green_fund_share": "0.075 AVS",
    "green_fund_share_in_wei": 75000000000000000,
    "miner_share": "1.425 AVS",
    "miner_share_in_wei": 1425000000000000000,
    "total_reward": "1.5 AVS",
    "total_reward_in_wei": 1500000000000000000
  }
  ```

- **Description**:
  - `block_number`: Current block height.
  - `total_reward`: Total block reward in AVS.
  - `miner_share`: Miner’s share of the block reward (95%) in AVS.
  - `green_fund_share`: Green fund’s share of the block reward (5%) in AVS.
  - Values are also provided in Wei for precision.

---

#### **Example Usage**
- **Using `curl`**:
  ```bash
  curl http://127.0.0.1:5000/current-reward
  ```

- **For a Pool UI**:
  Integrate the endpoint into your mining pool interface to display live reward updates.

---

#### **License**
This project is open-source and can be used freely under the MIT License. Please include proper attribution if used in your projects.

---

Feel free to reach out for improvements or additional features! 😊
