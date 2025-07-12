# Vue 3 + Vite

# 🌲 Gestor de Equipos Forestales

Aplicación web desarrollada como parte de la Evaluación N°4 de la asignatura *Programación Front End (TI2031)* de INACAP.

## 📌 Problemática

Las empresas forestales de la Región del Biobío enfrentan dificultades para llevar un registro ordenado de su maquinaria (como tractores, motosierras y drones), lo que puede provocar pérdidas, mal uso de los recursos y problemas en la gestión de mantenciones. Actualmente, muchos registros se hacen manualmente o con herramientas poco eficientes.

## ✅ Solución Propuesta

Se propone una aplicación web tipo **SPA** (Single Page Application), que permita registrar, modificar, eliminar y visualizar los equipos forestales en operación, usando tecnologías modernas de frontend. Además, se incorporan datos del clima de la región mediante una API pública.

### Tecnologías usadas:
- ⚙️ Vue 3 + Vite
- 🗃️ localStorage (persistencia local)
- 🌐 API pública: [Open-Meteo](https://open-meteo.com/)

## 🧩 Funcionalidades

- Agregar nuevos equipos con tipo, estado y fecha de adquisición.
- Editar o eliminar equipos registrados.
- Guardar datos de manera persistente con `localStorage`.
- Consultar el clima actual en la región del Biobío mediante una API externa.
- Aplicación modular con componentes personalizados.

## 🗂️ Estructura del Proyecto

/src
├── components
│ ├── ClimaZona.vue # Carga clima desde API pública
│ ├── EquipoForm.vue # Formulario para CRUD
│ └── ListaEquipos.vue # Visualiza y gestiona equipos
├── App.vue
└── main.js

## 🚀 Instrucciones de uso

1. Clona este repositorio:
   ```bash
   git clone https://github.com/tuusuario/gestor-equipos-forestales.git
   cd gestor-equipos-forestales
2. instala dependencias
npm install

3. ejecuta la aplicación en entorno local
npm run dev


Nombre completo: Jeral alejandro rios jara
Asignatura: Programación Front End
Carrera: Analista Programador
Sede: San Pedro de la Paz
Fecha: Julio 2025
