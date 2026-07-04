# 🫁 Pneumonia Detection System

Una aplicación **gratis en Hugging Face Spaces** para detectar neumonía en radiografías de tórax usando Deep Learning.

**🔗 Link en vivo:** (Será generado después del despliegue)

---

## 🚀 Despliegue Rápido (10 minutos)

### Opción 1: Subir a Hugging Face Spaces (RECOMENDADO)

1. **Crea una cuenta en [huggingface.co](https://huggingface.co)** (gratis)

2. **Crea un nuevo Space:**
   - Perfil → Spaces → Create Space
   - Name: `pneumonia-detector`
   - SDK: **Streamlit**
   - License: Apache 2.0
   - Visibility: Public

3. **Sube estos archivos:**
   ```
   app_huggingface.py → renombrarlo a app.py
   requirements.txt
   .gitignore
   .gitattributes
   ```

4. **Edita `app.py` línea 23:**
   - Reemplaza `MODEL_URL` con un link a tu modelo
   - Ver guía completa en `DEPLOY_GUIDE_HF_SPACES.md`

5. **¡Listo!** Espera 2-5 minutos y tu app estará online

---

## ⚙️ Tecnologías

- **Framework:** Streamlit
- **Deep Learning:** TensorFlow 2.17 + Keras
- **Modelo:** EfficientNetV2 (entrenado en Google Colab)
- **Hosting:** Hugging Face Spaces (GRATIS)

---

## 📊 Features

✅ Carga imágenes de rayos X (JPG, PNG)  
✅ Predicción en tiempo real  
✅ Confianza de la predicción (%)  
✅ Historial de análisis  
✅ Información del paciente  
✅ Recomendaciones médicas  

---

## 📚 Docs Completa

Ver archivo: [DEPLOY_GUIDE_HF_SPACES.md](DEPLOY_GUIDE_HF_SPACES.md)

---

## 💾 Estructura del Proyecto

```
.
├── app_huggingface.py         # App principal (renombar a app.py para HF)
├── requirements.txt            # Dependencias
├── best_effnetv2.keras        # Modelo (no subir, usar URL)
├── .gitattributes             # Config para Git LFS
├── .gitignore
├── DEPLOY_GUIDE_HF_SPACES.md  # Guía paso a paso
└── README.md                  # Este archivo
```

---

## ⚠️ Notas Importantes

- El archivo `best_effnetv2.keras` **NO se sube directamente** a Spaces
- Se descarga automáticamente desde una URL en tiempo de ejecución
- Esto mantiene el repositorio pequeño y el despliegue rápido

---

## 🎯 Next Steps

1. Sigue la guía en `DEPLOY_GUIDE_HF_SPACES.md`
2. Prepara la URL de tu modelo en GitHub
3. ¡Prueba la app!

