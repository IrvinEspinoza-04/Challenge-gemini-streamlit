# Simulador de Entrevistas Técnicas con IA

Aplicación académica con Python, Streamlit y el SDK `google-genai`. Simula una entrevista adaptativa de exactamente tres preguntas y genera un reporte final en Markdown.

## Archivos

- `app.py`: aplicación principal.
- `requirements.txt`: dependencias.

## Ejecutar localmente

1. Instala Python 3.10 o superior.
2. Instala las dependencias:

   ```bash
   pip install -r requirements.txt
   ```

3. Crea una carpeta `.streamlit` y dentro el archivo `secrets.toml`:

   ```toml
   GEMINI_API_KEY = "PEGA_AQUI_TU_CLAVE"
   ```

4. Ejecuta:

   ```bash
   streamlit run app.py
   ```

No subas `secrets.toml` a GitHub. Agrega `.streamlit/secrets.toml` a `.gitignore`.

## Publicar en Streamlit Community Cloud

1. Crea un repositorio en GitHub y sube `app.py` y `requirements.txt`.
2. Entra a https://share.streamlit.io/ y conecta GitHub.
3. Crea una aplicación seleccionando el repositorio y `app.py`.
4. En los ajustes de la aplicación, abre **Secrets** y agrega:

   ```toml
   GEMINI_API_KEY = "TU_CLAVE_DE_GEMINI"
   ```

5. Guarda y espera a que termine el despliegue. Copia la URL `*.streamlit.app`.

## Casos de prueba sugeridos

- Selecciona cada vacante y comprueba que los temas correspondan al rol.
- Envía tres respuestas técnicas y verifica que aparece el reporte sin una cuarta pregunta.
- Escribe una petición fuera de tema y comprueba que el entrevistador te redirija a la pregunta pendiente.
- Pulsa **Reiniciar Entrevista** y comprueba que el contador vuelve a 0 y se borra el historial.

La clave de Gemini se debe mantener en Secrets o en una variable de entorno, nunca dentro del código fuente.
