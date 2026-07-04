# 🚀 Guía de Despliegue en Hugging Face Spaces (GRATIS)

## ⚡ Opción más rápida (10 minutos)

### Paso 1: Preparar tu repositorio local
```bash
# Asegúrate de estar en tu carpeta del proyecto
cd tu-proyecto-neumonia

# Inicializa Git si no lo has hecho
git init
git add .
git commit -m "Initial commit - Pneumonia detector"
```

### Paso 2: Crear un Space en Hugging Face
1. Ve a [huggingface.co](https://huggingface.co)
2. Inicia sesión (crea cuenta si no tienes)
3. Haz click en tu perfil → **"Spaces"** → **"Create new Space"**
4. Configuración:
   - **Space name:** `pneumonia-detector` (o el que prefieras)
   - **License:** Apache 2.0
   - **Space SDK:** Streamlit ✅
   - **Visibility:** Public
   - Click **"Create Space"**

### Paso 3: Subir archivos (OPCIÓN A - SIN el modelo en el repositorio)

Elige **UNA** de estas opciones:

#### 🟢 **Opción A1: Descargar modelo en tiempo de ejecución (MÁS FÁCIL)**

1. Sube tu modelo a GitHub:
   ```bash
   # En GitHub: Crea un nuevo repo llamado "pneumonia-model"
   # Sube aquí el archivo best_effnetv2.keras
   ```

2. En tu Space, sube estos archivos SOLO:
   - `app_huggingface.py` → renómbralo a `app.py`
   - `requirements.txt` (versión actualizada abajo)

3. Edita `app.py` y reemplaza la línea:
   ```python
   MODEL_URL = "https://github.com/TU_USUARIO/pneumonia-model/raw/main/best_effnetv2.keras"
   ```

#### 🔵 **Opción A2: Usar Git LFS (para subir el modelo)**

1. En tu máquina local, instala Git LFS:
   ```bash
   # En Windows (PowerShell como admin):
   choco install git-lfs
   # O descargar desde: https://git-lfs.github.com/
   ```

2. Configura Git LFS en tu carpeta:
   ```bash
   git lfs install
   git lfs track "*.keras"
   git add .gitattributes
   git commit -m "Add Git LFS tracking"
   ```

3. Sigue los pasos en el Space para conectar tu repositorio local

### Paso 4: Actualizar requirements.txt

Asegúrate que contenga ESTO (actualizado para HF Spaces):
```txt
streamlit==1.39.0
tensorflow==2.17.0
pillow==10.4.0
numpy==1.26.4
pandas==2.2.2
```

### Paso 5: ¡Listo! 

Espera 2-5 minutos y tu app estará en:
```
https://huggingface.co/spaces/TU_USUARIO/pneumonia-detector
```

---

## 📊 Comparativa de Opciones

| Opción | Ventajas | Desventajas | Tiempo |
|--------|----------|-------------|--------|
| **A1 (GitHub URL)** | ✅ Fácil, sin Git LFS | Necesita URL válida | 10 min |
| **A2 (Git LFS)** | ✅ Todo en un lugar | ⚠️ Requiere setup | 15 min |

---

## ⚠️ Solución de problemas

### "Model not found" error
- Asegúrate que `MODEL_URL` apunta a un archivo real
- Prueba la URL en el navegador

### "TensorFlow out of memory"
- HF Spaces tiene 16GB RAM, debería ser suficiente
- Si falla: comprime el modelo con cuantización

### La app tarda en cargar la primera vez
- Normal: está descargando el modelo (~200MB)
- Las siguientes cargas serán rápidas

---

## 🎯 Próximos pasos

- Sube imágenes de prueba para verificar funciona
- Modifica `MODEL_URL` según tu estrategia
- ¡Comparte el link con médicos!

