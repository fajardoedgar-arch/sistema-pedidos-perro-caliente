# 🌭 Sistema Web de Gestión de Pedidos — El Perro Caliente

> **Actividad 2 — Ingeniería de Software**  
> Edgar Fajardo Molinares | Facilitadora: Clara Lucía Monsalve Ríos  
> Fundación Universitaria Católica del Norte — Marzo 2026

---

## 📋 Descripción del Proyecto

Sistema web para gestionar pedidos en un puesto de comida rápida. Permite registrar órdenes, hacer seguimiento del estado de preparación, controlar el inventario de ingredientes y generar reportes de ventas diarios.

**Analogía del proyecto:** Así como en la cocina cada ingrediente tiene su rol y el proceso sigue una receta, este sistema digitaliza ese flujo asegurando que cada pedido llegue correctamente al cliente.

---

## 📁 Contenido del Repositorio

```
📦 sistema-pedidos-perro-caliente/
├── 📄 README.md                          ← Este archivo
├── 📂 docs/
│   ├── 📄 Plan_de_Pruebas.docx           ← Plan de pruebas completo con casos y evidencias
│   ├── 📄 Manual_de_Usuario.docx         ← Manual básico de usuario del sistema
│   └── 📄 Soporte_y_Tecnologias.docx     ← Estrategia post-proyecto + descripción tecnológica
├── 📂 src/
│   ├── 📂 frontend/                      ← HTML, CSS, JavaScript de la interfaz
│   ├── 📂 backend/                       ← Servidor Node.js + Express (API REST)
│   └── 📂 database/                      ← Scripts SQL de creación e inserción de datos
└── 📄 .gitignore
```

---

## 🧪 Plan de Pruebas

El plan de pruebas completo se encuentra en `docs/Plan_de_Pruebas.docx`. A continuación, un resumen de los casos ejecutados:

| ID | Caso de Prueba | Tipo | Prioridad | Estado |
|----|----------------|------|-----------|--------|
| CP-001 | Registro de pedido exitoso | Funcional | Alta | ✅ APROBADO |
| CP-002 | Validación ingredientes no disponibles | Funcional | Alta | ✅ APROBADO |
| CP-003 | Cambio de estado del pedido | Funcional | Alta | ✅ APROBADO |
| CP-004 | Autenticación con credenciales inválidas | Seguridad | Alta | ✅ APROBADO |
| CP-005 | Rendimiento bajo carga (20 usuarios) | Rendimiento | Media | ✅ APROBADO |
| CP-006 | Compatibilidad en navegador móvil | Compatibilidad | Media | ✅ APROBADO |
| CP-007 | Generación de reporte diario | Funcional | Media | ✅ APROBADO |
| CP-008 | Cierre de sesión y limpieza de caché | Seguridad | Alta | ✅ APROBADO |

**Resultado general:** 8/8 casos aprobados (100%) — Sin defectos críticos.

### Estrategia de Pruebas

Se aplicó un enfoque incremental por sprints con los siguientes tipos de prueba:
- **Unitarias** — Jest (Node.js)
- **Funcionales e Integración** — Selenium + Postman
- **Rendimiento** — Apache JMeter (20 usuarios simultáneos; tiempo respuesta promedio: 1.8 s)
- **Seguridad** — OWASP ZAP + revisión manual
- **Compatibilidad** — Chrome, Firefox, Edge, Chrome Mobile

---

## 👤 Manual de Usuario

Consultar `docs/Manual_de_Usuario.docx` para instrucciones detalladas. Resumen rápido:

### Perfiles de acceso
| Perfil | Funciones |
|--------|-----------|
| **Administrador** | Gestión completa: usuarios, inventario, reportes |
| **Cocinero** | Ver pedidos en cola, actualizar estado de preparación |
| **Empleado de servicio** | Registrar pedidos, confirmar entrega |

### Flujo principal
1. Acceder a `https://pedidos.elperrocaliente.com`
2. Iniciar sesión con credenciales asignadas
3. Registrar nuevo pedido → seleccionar producto e ingredientes → confirmar
4. Seguir el pedido en el panel: Recibido → En preparación → Listo → Entregado
5. Generar reporte diario desde Menú > Reportes

---

## 🔧 Tecnologías Utilizadas

| Capa | Tecnología | Versión | Justificación |
|------|-----------|---------|---------------|
| Frontend | HTML5 + CSS3 + JavaScript | ES2022 | Estándar web, sin dependencias innecesarias |
| Frontend | Bootstrap | 5.3 | Responsive design para PC y tablets |
| Backend | Node.js + Express.js | 20 LTS / 4.18 | Un solo lenguaje full-stack, API REST ágil |
| Base de datos | MySQL | 8.0 | Datos relacionales + ACID compliance |
| Control de versiones | Git + GitHub | 2.x | Estándar de la industria |
| Gestión del proyecto | Trello | Web | Kanban visual accesible para el Product Owner |
| Servidor web | Nginx | 1.24 | Proxy inverso de alto rendimiento |
| Hosting | Digital Ocean VPS | Ubuntu 22.04 | Costo-eficiente para negocio pequeño ($6/mes) |

> Todas las tecnologías son de código abierto o freemium. Sin costos de licencias.

---

## 🛡️ Estrategia de Soporte Post-Proyecto

Consultar `docs/Soporte_y_Tecnologias.docx` para el documento completo. Resumen:

### Fases de soporte
- **Fase 1 — Estabilización (Semanas 1–4):** Monitoreo diario, corrección de bugs residuales, retroalimentación inicial.
- **Fase 2 — Soporte Activo (Meses 2–6):** Canal de soporte por email, backups automáticos diarios, actualizaciones de seguridad.
- **Fase 3 — Mantenimiento Evolutivo (Mes 7+):** Nuevas funcionalidades por sprints, revisión trimestral de prioridades.

### Niveles de atención
| Nivel | Tipo | Tiempo de Respuesta |
|-------|------|---------------------|
| P1 — Crítico | Sistema caído | ≤ 4 horas |
| P2 — Alto | Funcionalidad principal no disponible | ≤ 24 horas |
| P3 — Medio | Funcionalidad secundaria con falla | ≤ 72 horas |
| P4 — Bajo | Mejora de usabilidad | Próxima iteración |

### Canales de soporte
- 📧 Correo: soporte@elperrocaliente.com
- 🐛 GitHub Issues: abrir un issue con etiqueta `bug`, `enhancement` o `question`
- 📅 Reunión mensual de seguimiento con el Product Owner

---

## 🚀 Cómo Ejecutar el Proyecto (Desarrollo Local)

```bash
# 1. Clonar el repositorio
git clone https://github.com/edgar-fajardo/sistema-pedidos-perro-caliente.git
cd sistema-pedidos-perro-caliente

# 2. Instalar dependencias del backend
cd src/backend
npm install

# 3. Configurar base de datos
# Importar src/database/schema.sql en MySQL
mysql -u root -p < src/database/schema.sql

# 4. Configurar variables de entorno
cp .env.example .env
# Editar .env con las credenciales de tu base de datos local

# 5. Iniciar servidor
npm start
# Servidor disponible en http://localhost:3000
```

---

## 📊 Estado del Proyecto

- [x] Sprint 1 — Autenticación y estructura base
- [x] Sprint 2 — Módulo de pedidos (backend)
- [x] Sprint 3 — Integración de módulos
- [x] Sprint 4 — Testing y corrección de defectos
- [x] Despliegue en producción
- [ ] v1.1 — Integración de pagos digitales *(planificado)*
- [ ] v1.2 — Notificaciones por WhatsApp *(planificado)*

---

## 👨‍💻 Autor

**Edgar Fajardo Molinares**  
Ingeniería Informática — Fundación Universitaria Católica del Norte  
Facilitadora: Clara Lucía Monsalve Ríos  

---

*"Así como en la cocina no improvisamos sin receta, en ingeniería de software no desarrollamos sin metodología."*
