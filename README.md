# MLP‑MNIST

> Ajuste y optimización de un **Perceptrón Multicapa (MLP)** en PyTorch para el reconocimiento de dígitos manuscritos con **MNIST**.

![Training curves](assets/accuracy_loss_curves.gif)

---

## ✨ Características principales

| Módulo             | Descripción                                                                   |
| ------------------ | ----------------------------------------------------------------------------- |
| **PyTorch ➡️ MLP** | Arquitectura configurable (hasta 3 capas ocultas, *dropout* y *batch‑norm*)   |
| **Optuna Search**  | Búsqueda bayesiana de hiperparámetros (tamaño de capas, `lr`, *weight‑decay*) |
| **Schedulers**     | `ReduceLROnPlateau` + exploración de *learning rate finder*                   |
| **Early Stopping** | Basado en la métrica *validation accuracy* con *patience* configurable        |
| **Plotly Dash**    | Dashboard interactivo con curvas de pérdida/precisión y matriz de confusión   |

---

## 📂 Estructura del proyecto

```
mlp-mnist/
├── data/              # Descarga automática de MNIST
├── src/
│   ├── datamodule.py  # PyTorch Lightning DataModule
│   ├── model.py       # Definición del MLP
│   ├── train.py       # Entrenamiento con callbacks (CLI)
│   └── tune.py        # Búsqueda con Optuna
├── dashboards/        # Notebooks y app Dash para visualización
├── assets/            # Figuras y gifs para el README
├── requirements.txt
└── README.md
```

---

## ⚙️ Requisitos

```bash
python >= 3.9
pytorch >= 2.2
pytorch‑lightning >= 2.2
optuna >= 3.6
plotly >= 5.20
pandas scikit‑learn tqdm rich
```

Instalación rápida:

```bash
pip install -r requirements.txt
```

---

## 🚀 Entrenamiento rápido

```bash
# Entrenamiento con hiperparámetros por defecto\ npython src/train.py --epochs 20 --batch_size 256

# Búsqueda de 50 ensayos con Optuna
python src/tune.py --trials 50 --timeout 3600
```

Los modelos, logs y checkpoints se almacenan en `runs/`.

### Visualización

```bash
# Abre el dashboard Plotly Dash
python dashboards/app.py
```

---

## 📊 Resultados

| Métrica               | Valor      |
| --------------------- | ---------- |
| Test Accuracy         | **98.4 %** |
| Parámetros            | 1.1 M      |
| Mejor *learning rate* | 0.0008     |

*Comparación completa dentro de la carpeta `reports/`.*

---

## 📜 Licencia

Distribuido bajo la licencia MIT © 2025 **Fernando NasserEddine López**.

---

## 🙌 Créditos y recursos

* [PyTorch Lightning Docs](https://lightning.ai/docs)
* [Optuna Examples](https://github.com/optuna/optuna-examples)
* Dataset [MNIST](http://yann.lecun.com/exdb/mnist/) (LeCun 1998)

Si utilizas este repositorio en tu investigación o docencia, por favor, cítalo o déjame un *star* ⭐️.

