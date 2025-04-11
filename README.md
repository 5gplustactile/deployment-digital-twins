# deployment-digital-twins

Este repositorio está diseñado para gestionar **gemelos digitales como código**.

---

## Propósito

El objetivo principal de este repositorio es:
- Centralizar plantillas y configuraciones necesarias para los despliegues de gemelos digitales.
- Automatizar procesos mediante pipelines integrados y ArgoCD.
- Proveer ejemplos prácticos para la personalización de gemelos digitales en diferentes entornos.
- Facilitar la colaboración entre equipos dentro del proyecto **5G+TACTILE**.

---

## Estructura del Repositorio

- **`demo/`**: Configuración específica para el entorno demo.
  - `main.yaml`: Archivo principal de configuración para la demo.

- **`examples/`**: Directorio con ejemplos prácticos para personalizar y desplegar gemelos digitales.
  - **`digital-twins/`**: Plantillas base para configuraciones de gemelos digitales.
    - `whoami/`: Ejemplo práctico con Kustomize.

- **`opentwins/`**: Configuración específica para el entorno **OpenTwins**.
  - `main.yaml`: Archivo principal de despliegue en OpenTwins.

- **`telefonica/`**: Configuraciones de gemelos digitales y servicios específicos para Telefónica.
  - `main.yaml`: Archivo principal de configuración.

---

## Procedimiento

### **Creación de un Gemelo Digital (DT):**

1. **Clonar el repositorio y crear una rama:**
   - Navega al repositorio `deployment-digital-twins`.
   - Crea una nueva rama utilizando el siguiente formato:
     ```bash
     git checkout -b dt/NOMBRE_DT
     ```
     Esta rama será el espacio de trabajo para almacenar la configuración de la aplicación ArgoCD correspondiente al gemelo digital (por ejemplo, `telefonica/main.yaml`).

2. **Agregar el contenido de la aplicación ArgoCD:**
   - Usa la plantilla proporcionada en `examples/digital-twin/main.yaml`.
   - Agrega esta plantilla al archivo `main.yaml` en el espacio de trabajo correspondiente, por ejemplo, `telefonica/main.yaml`.
   - Asegúrate de que el campo `spec.destination.server` apunte al endpoint donde se desplegará el gemelo digital.
   - Revisa todos los cambios en el archivo `main.yaml` y súbelos a la rama `dt/NOMBRE_DT`:
     ```bash
     git add .
     git commit -m "Crear gemelo digital NOMBRE_DT"
     git push origin dt/NOMBRE_DT
     ```

3. **Ejecutar el pipeline:**
   - Una vez que los cambios se suben al repositorio, se activará automáticamente un pipeline.
   - Este pipeline creará un **Pull Request (PR)** desde la rama `dt/NOMBRE_DT` hacia la rama principal (`main`).
   - Espera a que todos los pasos del pipeline se completen con éxito.

4. **Fusionar los cambios:**
   - Revisa el PR generado y fusiónalo en la rama principal (`main`).
   - Esto activará un nuevo pipeline para adaptar la configuración de la aplicación ArgoCD (`main.yaml`) al entorno objetivo.

5. **Verificar el despliegue en ArgoCD:**
   - Accede a la interfaz gráfica de **ArgoCD**.
   - Filtra por el proyecto `digital-twins` para visualizar los objetos creados.
   - Confirma que los recursos se hayan desplegado correctamente.

---

## Notas

- Utiliza la plantilla ubicada en `examples/digital-twin/main.yaml` como base para la configuración.
- Asegúrate de conocer el endpoint del clúster (`spec.destination.server`) antes de realizar el despliegue.
- Todos los cambios deben ser revisados y validados antes de realizar la fusión.

---

Este repositorio es mantenido como parte del proyecto **5G+TACTILE**.

---

## Licencia

Este projecto es licenciado bajo [Apache](LICENSE)