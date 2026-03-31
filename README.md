# KGEmbeddings-4-XS

## 🧠 Decision Game Ontology (DGO)

<img width="1831" height="1190" alt="image" src="https://github.com/user-attachments/assets/3f67fa83-edb5-4163-bd30-0f901fac2661" />


The **Decision Game Ontology (DGO)** models how individuals make decisions in structured game settings, including competitive, cooperative, and mixed-motive scenarios.

Rather than focusing on a specific domain (e.g., conflict), the ontology captures the **general structure of decision-making in games**, making it flexible across different experimental setups.

---

## 🎯 Core Idea

At the heart of the ontology is the concept of a **Decision Event**.

A `DecisionEvent` represents a **single, situated decision** made by a participant within a specific context. This includes:

- who is making the decision  
- in which game and round it occurs  
- the interaction context  
- the role of the participant  

This design allows us to represent decisions not as isolated values, but as **context-dependent events**.

---

## 🧩 Main Components

### 👤 Participant
Represents an individual taking part in the game.

Each participant is described through:
- identity category  
- generosity profiles (GPS1 & GPS2)  
- home country  

---

### 🎮 Game → 🔁 Round → 🤝 Interaction

The environment is structured hierarchically:

- **Game** → defines the general setup (e.g., game type)  
- **Round** → captures repeated interactions  
- **Interaction** → encodes the social context, including:
  - group relation (ingroup, outgroup, stranger)
  - opponent country  
  - interaction type (competitive, cooperative, mixed)

---

### ⚙️ DecisionEvent (central node)

This is the key modeling choice.

A `DecisionEvent` connects all relevant elements:

- `Participant`
- `Game`
- `Round`
- `Interaction`
- `Role`

👉 This creates a **rich relational neighborhood**, which is particularly important for knowledge graph embeddings.

---

### 🌍 Country

Countries are linked both to participants (home country) and interactions (opponent country), and are enriched with:

- GDP category  
- GINI category  

This allows socio-economic context to influence the decision structure.

---

### 🏷️ Concept Nodes

All important features are modeled as **entities (not literals)**:

- Role  
- GameType  
- GroupRelation  
- IdentityCategory  
- Generosity categories  
- GDP / GINI categories  

This is intentional:

👉 It makes the ontology **embedding-friendly**, since KG embedding models learn from relationships between entities.

---

## 🔎 Traceability Layer

While the ontology is optimized for relational structure, it also preserves the original data through **data properties**, such as:

- raw scores (identity, generosity, GDP, GINI)  
- z-scores  
- participant ID  
- ISO country codes  
- raw decision values  

These are included for:
- reproducibility  
- auditing  
- detailed querying  

but are **not the primary signal for embeddings**.

---

## 🤖 Why this design?

The ontology is specifically designed to support:

- knowledge graph embeddings  
- clustering and similarity analysis  
- predictive modeling  

The key principle is:

👉 **Structure over raw numbers**

Relational patterns (who, where, in which context) are emphasized over isolated numeric values.

---

## 📜 License

This project is released under the **Apache 2.0 License**.


