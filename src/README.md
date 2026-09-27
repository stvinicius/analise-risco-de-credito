# src

Use esta pasta para guardar funções reutilizáveis à medida que você extrai lógica repetida dos notebooks (por exemplo: `preprocessing.py`, `features.py`, `evaluation.py`).

Sugestão de fluxo: primeiro explore e prototipe nos notebooks; quando uma função estiver estável e for usada em mais de um notebook, mova-a para um módulo aqui e importe de volta (`from src.preprocessing import ...`).
