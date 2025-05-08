# Distributed File Storage System with Encryption & Fault Tolerance

This project simulates a **Distributed File Storage System** using Python. It includes secure file encryption, node replication, fault-tolerant file retrieval, and role-based access control for file operations.

---

## 📦 Features

- ✅ Upload files with encryption
- ✅ Store files in simulated distributed nodes
- ✅ Role-based file access (Admin/Viewer)
- ✅ Edit file content (Admins only)
- ✅ Fault tolerance with node failure simulation
- ✅ AES encryption with key storage
- ✅ SQLite-based metadata tracking

---

## 🗂 Folder Structure

```
distributed-encrypted-file-storage/
├── src/                        # Main project source code
│   ├── dfs.py
│   ├── file_operations.py
│   ├── encryption_utils.py
│   ├── metadata_manager.py
│   └── decryption.py
├── metadata/                   # Generated encryption keys and metadata DB
├── storage_node_1/             # Simulated distributed storage nodes
├── storage_node_2/
├── storage_node_3/
├── storage_node_4/
├── LICENSE.txt                 # MIT License
├── .gitignore                  # Ignore temp and log files
└── README.md                   # Project documentation
```

---

## ⚙️ How to Run

### 1. 📥 Install dependencies
```bash
pip install cryptography
```

### 2. 🧠 Generate encryption key and metadata DB
```bash
python src/metadata_manager.py
python src/file_operations.py  # run this and call generate_and_save_key() if needed
```

### 3. 📤 Upload a file (as admin)
```bash
python src/dfs.py upload --role admin --file example.txt --storage_node 1
```

### 4. 👀 View a file
```bash
python src/dfs.py view_content --role viewer --filename example.txt --key YOUR_KEY
```

> Replace `YOUR_KEY` with the string loaded from `metadata/encryption_key.key`

---

## 👥 Roles

- **Admin**: Can view and edit file content
- **Viewer**: Can only view decrypted content

---

## 🧪 Node Failure Simulation

You can define unavailable nodes inside `file_operations.py` in the list:
```python
unavailable_nodes = [1, 2, 3]
```
The system will try other available nodes automatically.

---

## 🧰 Technologies Used

- Python 3
- Cryptography (AES, Fernet)
- SQLite
- Argparse (for CLI)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE.txt).
