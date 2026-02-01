# 🎯 CCAI Ops Hub - Task Manager

Dashboard minimalista para gestión de tareas con sincronización automática a GitHub Issues y Projects.

## ✨ Características

- 🎨 **Diseño blanco minimalista** - Interfaz limpia y moderna
- 📋 **Kanban Board** - 3 columnas: Pendiente, En Progreso, Completado
- 🔄 **GitHub Sync bidireccional** - Sincroniza tareas con Issues y Projects V2
- 💾 **Todo en un archivo** - Sin dependencias locales, solo CDNs

## 🚀 Uso Rápido

### 1. Iniciar servidor local
```bash
python3 -m http.server 8000
```

### 2. Abrir en navegador
```
http://localhost:8000
```

### 3. Configurar GitHub (primera vez)
1. Click en **"Config"**
2. Ingresar:
   - **Token**: Tu GitHub Personal Access Token
   - **Usuario**: `devlewiso`
   - **Repo**: `Todo_ProjectName`
   - **Project ID**: `2` (opcional)
3. Click en **"Guardar Config"**

### 4. Sincronizar tareas
- **Desde GitHub → Dashboard**: Click en **"Sync from GitHub"**
- **Desde Dashboard → GitHub**: Automático al crear tareas

## 🔑 GitHub Token

Crea tu token en: https://github.com/settings/tokens

**Permisos necesarios:**
- ✅ `repo` (acceso a repositorios)
- ✅ `project` (acceso a Projects)

## 📊 Flujo de Trabajo

```
1. Crear tarea en Dashboard
   ↓
2. Se crea Issue en GitHub automáticamente
   ↓
3. Se agrega al Project (si está configurado)
   ↓
4. Click en "Sync from GitHub" para cargar Issues existentes
```

## 🗂️ Estructura

```
Todo_ProjectName/
├── index.html    ← Todo el código (HTML + CSS + JS)
└── README.md     ← Este archivo
```

## 🎨 Personalización

Edita las variables CSS en `index.html` (líneas 13-24):

```css
:root {
    --bg: #F8FAFC;
    --surface: #FFFFFF;
    --accent: #6366F1;
    --success: #10B981;
    --warning: #F59E0B;
    --danger: #EF4444;
}
```

## 📝 Notas

- El token se guarda en `localStorage` del navegador
- Las tareas se cargan desde GitHub Issues al hacer sync
- Los Issues se crean con formato: `[Estado] Título`
- Las prioridades se mapean a labels: `high`, `medium`, `low`

---

**© NeuralCodeLab | CCAI Operations Hub**  
*Versión 2.0 - Febrero 2026*
