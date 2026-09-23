# Mon aide-mémoire curl

Une entrée par quête. Trois lignes chacune, écrites avec mes mots.

- **La situation** — ce que la quête demandait
- **La commande** — celle qui a validé, recopiée telle quelle
- **Le piège** — ce qui m'a coincé, ou rien si tout a coulé

---

## 1 — Day 1: Inventory Check

**La situation** :

**La commande** :

```bash
curl http://localhost:8080/inventory
```

**Le piège** :

---

## 2 — Day 2: Adding Items

**La situation** :

**La commande** :

```bash
curl -s -X POST -H "Content-Type: application/json" -d '{"name":"Butter"}' http://localhost:8080/inventory
```

**Le piège** :

---

## 3 — Day 3: Maintain and Update

**La situation** :

**La commande** :

```bash
curl -s -X PATCH -H "Content-Type: application/json" -d '{"name:"Organic Bananas"}' http://localhost:8080/inventory/1
curl -s -X PUT -H "Content-Type: application/json" -d '{"name:"In stock Watermelon", "price":"5.00"}' http://localhost:8080/inventory/2
curl -s -X DELETE http://localhost:8080/inventory/3
```

**Le piège** :

---

## 4 — The Elemental Search

**La situation** :

**La commande** :

```bash
curl -s http://localhost:8080/pokemon/search?type=fire
curl -s http://localhost:8080/pokemon/search?type=fire&role=special+attacker
```

**Le piège** :

---

## 5 — Payslip Uploader

**La situation** :

**La commande** :

```bash
curl -s -o payslip.json http://localhost:8080/files/payslip
```

**Le piège** :

---

## 6 — Strict API Contracts

**La situation** :

**La commande** :

```bash
curl -s -X GET -H "x-api-key: secret123" http://localhost:8080/groceries

```

**Le piège** :

---

## 7 — The Manager's Secret

**La situation** :

**La commande** :

```bash

```

**Le piège** :

---

## 8 — The Galactic Relay

**La situation** :

**La commande** :

```bash

```

**Le piège** :
