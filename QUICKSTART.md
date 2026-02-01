# 🚀 Guía Rápida - CCAI Ops Dashboard con GitHub Sync

## ✅ Sistema Completado

Tu dashboard ahora tiene **sincronización automática con GitHub**. Cada vez que creas, editas o eliminas una tarea, se crea/actualiza un Issue en tu repositorio de GitHub.

---

## 🔧 Configuración Inicial (Solo una vez)

### 1. Abrir el Dashboard

```bash
# Opción recomendada: Servidor local (evita CORS)
cd /home/devlewiso/Desktop/git/Todo_ProjectName
python3 -m http.server 8000

# Luego abrir en navegador:
# http://localhost:8000
```

### 2. Configurar GitHub

1. **Click en el botón "⚙️ Configuración"** (esquina superior derecha)
2. Llenar el formulario:
   - **GitHub Token**: `YOUR_GITHUB_TOKEN`
   - **Usuario**: `YOUR_GITHUB_USERNAME`
   - **Repositorio**: `YOUR_GITHUB_REPO`
   - **Sincronización Automática**: `Activada` ✅
3. Click en **"Guardar Configuración"**

✅ **Listo!** El botón de configuración mostrará un **punto verde** indicando que está configurado.

---

## 🎯 Cómo Funciona

### Sincronización Automática

Cuando la sincronización automática está **activada**:

| Acción | Qué pasa en GitHub |
|--------|-------------------|
| ✨ **Crear tarea** | Se crea un nuevo Issue |
| ✏️ **Editar tarea** | Se crea un nuevo Issue con los datos actualizados |
| 🗑️ **Eliminar tarea** | No se elimina el Issue (GitHub no permite eliminar Issues vía API) |

### Sincronización Manual

Si prefieres sincronizar manualmente:

1. En configuración, selecciona **"Desactivada (solo manual)"**
2. Usa el botón **"Sync Manual"** cuando quieras sincronizar todas las tareas

---

## 📋 Uso Diario

### Crear Nueva Tarea

1. Click en **"+ Nueva Tarea"**
2. Llenar formulario:
   - **Título**: Descripción de la tarea
   - **Responsable**: Seleccionar (Manager, Prime 1/2, DevOps, Analista 1-7)
   - **Prioridad**: Alta / Media / Baja
   - **Estado**: Pendiente / En Progreso / Completado
   - **Fecha**: Click en el campo para abrir el **calendario widget** 📅
3. Click en **"Guardar Tarea"**

✅ **Automáticamente** se crea un Issue en GitHub

### Editar Tarea Existente

1. **Click en cualquier tarjeta de tarea** (en el tablero Kanban)
2. Se abre el modal de edición con todos los datos
3. Modificar lo que necesites
4. Click en **"Guardar Cambios"**

✅ **Automáticamente** se actualiza en GitHub

### Eliminar Tarea

1. Click en la tarea para editarla
2. Click en el botón rojo **"🗑️ Eliminar"**
3. Confirmar eliminación

⚠️ **Nota**: El Issue en GitHub no se elimina (limitación de la API)

---

## 🔍 Verificar Sincronización

### En el Dashboard

- Abre la **Consola del Navegador** (F12)
- Verás mensajes como:
  ```
  ✅ Issue #123 creado: https://github.com/devlewiso/Todo_ProjectName/issues/123
  ```

### En GitHub

1. Ve a tu repositorio: https://github.com/devlewiso/Todo_ProjectName
2. Click en la pestaña **"Issues"**
3. Verás todos los Issues creados desde el dashboard

Cada Issue tendrá:
- **Título**: `[Estado] Nombre de la tarea`
- **Labels**: prioridad, estado, rol, etiqueta
- **Descripción**: Todos los detalles de la tarea

---

## 🎨 Características del Dashboard

### ✅ Implementadas

- ✅ **Kanban Board** con 3 columnas (Pendiente, En Progreso, Completado)
- ✅ **Click en tarjetas** para editar
- ✅ **Calendario Widget** visual (Flatpickr)
- ✅ **Filtros por Rol** (Manager, Primes, DevOps, Analistas)
- ✅ **Estadísticas en Tiempo Real**
- ✅ **Sincronización Automática con GitHub**
- ✅ **Configuración Segura** (token en localStorage)
- ✅ **Tema Oscuro Profesional**
- ✅ **Responsive Design**

---

## 🔒 Seguridad del Token

### ¿Dónde se guarda el token?

- **localStorage** del navegador (solo en tu computadora)
- **NO** se sube al repositorio de GitHub
- **NO** está en ningún archivo del proyecto

### ¿Cuánto dura?

- Hasta que cierres la sesión del navegador
- O hasta que hagas click en **"Limpiar"** en configuración

### ¿Es seguro?

- ✅ Sí, solo tú tienes acceso
- ⚠️ **NUNCA** compartas tu token con nadie
- ⚠️ **NUNCA** lo subas a GitHub en el código

---

## 📊 Estructura del Equipo

```
👔 Manager General (1)
   └── Presenta proyectos y consigue financiamiento

👨‍💼 Primes (2)
   └── Coordinan entregas entre analistas y DevOps

⚙️ DevOps (1)
   └── Infraestructura y deployment

👨‍💻 Analistas (7)
   └── Tareas específicas del proyecto CCAI
```

---

## 🐛 Troubleshooting

### El token no funciona

1. Verifica que el token tenga los permisos correctos:
   - ✅ `repo` (acceso completo a repositorios)
   - ✅ `project` (acceso a GitHub Projects)
2. Verifica que el token no haya expirado
3. Genera un nuevo token si es necesario

### No se sincronizan las tareas

1. Abre la consola del navegador (F12)
2. Busca errores en rojo
3. Verifica que:
   - El token esté configurado
   - El usuario y repositorio sean correctos
   - Tengas conexión a internet

### CORS Error (al cargar tareas)

- **Solución**: Usa un servidor local
  ```bash
  python3 -m http.server 8000
  ```
- No abras el archivo directamente (`file://`)

---

## 📝 Próximos Pasos

### Opcional: Crear GitHub Project

1. En tu repo, ve a **Projects** → **New Project**
2. Nombre: "CCAI Ops Hub"
3. Template: "Board"
4. Los Issues creados aparecerán automáticamente

### Opcional: Automatizar con GitHub Actions

Puedes crear un workflow que:
- Actualice el `sprint_tasks.json` cuando se crea un Issue
- Sincronice bidireccional (GitHub → Dashboard)

---

## 🎉 ¡Listo!

Tu dashboard está completamente funcional y sincronizado con GitHub.

**Cada cambio que hagas se reflejará automáticamente en tu repositorio** 🚀

---

**© NeuralCodeLab | CCAI Operations Hub**  
*Versión 2.0.0 - Enero 2026*
