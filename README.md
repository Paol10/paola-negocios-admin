# Paola Negocios - Admin Central

**Plataforma centralizada para administración, automatización y marketing de múltiples negocios.**

Autor: Paola García Chavez  
Email: garciaangie925@gmail.com  
Última actualización: 2026-09-04

---

## 📋 Contenido

### 🏢 Negocios Activos

- **Monarca Cocinas Integrales** (Estado de México)
  - Sitio web: monarcacocinas.com
  - CRM: Kommo
  - Leads automatizados: N8N + Webhooks
  - Admin: `/monarca`

- **Voy a Vender con IA** (Colombia)
  - Landing page: voy-a-vender-colombia
  - Servicios: WhatsApp IA + Videos + Sitio
  - Paquetes: Arranque, Motor, Piloto
  - Status: En desarrollo

### 📁 Estructura de Carpetas

```
paola-negocios-admin/
│
├── docs/                          # Documentación centralizada
│   ├── procesos.md               # Procesos de operación
│   ├── arquitectura.md           # Arquitectura general
│   ├── checklist-nuevo-negocio.md # Template para nuevos clientes
│   └── plantillas/               # Templates reutilizables
│
├── kommo/                          # Configuración Kommo (CRM)
│   ├── monarca-pipeline.json     # Pipeline de Monarca
│   ├── campos-personalizados.md  # Campos custom por negocio
│   └── README.md                 # Guía Kommo
│
├── n8n/                            # Workflows de automatización
│   ├── workflows-monarca/        # Workflows específicos Monarca
│   │   ├── webhook-formulario.json
│   │   └── followup-leads.json
│   ├── workflows-compartidos/    # Reutilizables en otros negocios
│   └── README.md                 # Guía N8N
│
├── monarca/                        # Documentación Monarca
│   ├── instrucciones.md          # Setup y procesos
│   ├── clientes.md               # Cliente: Familia López, Arq. René
│   ├── problemas-resueltos.md    # Issues y soluciones
│   └── checklist-diario.md       # Tareas diarias
│
├── bots-telegram/                  # Bots automáticos
│   ├── @BelateParfumBot/
│   ├── @MonarcaBot/
│   └── README.md
│
├── scripts/                        # Utilidades automatizadas
│   ├── crear-nuevo-negocio.sh    # Scaffolding nuevo negocio
│   ├── backup-kommo.sh           # Backup de Kommo
│   └── sync-datos.sh             # Sincronización
│
└── README.md                       # Este archivo
```

---

## 🚀 Quick Start

### 1️⃣ Ver estado de Monarca
```bash
cd monarca
cat instrucciones.md
```

### 2️⃣ Ver workflows N8N
```bash
cd n8n
cat README.md
```

### 3️⃣ Ver configuración Kommo
```bash
cd kommo
cat README.md
```

### 4️⃣ Crear nuevo negocio
```bash
bash scripts/crear-nuevo-negocio.sh
```

---

## 📊 Dashboard de Proyectos

| Negocio | Estado | CRM | Automación | Sitio Web |
|---------|--------|-----|-----------|-----------|
| Monarca Cocinas | ✅ Activo | Kommo | N8N | monarcacocinas.com |
| Voy a Vender IA | 🟡 Desarrollo | - | - | voy-a-vender-colombia |
| (Próximo) | ⏳ Pendiente | - | - | - |

---

## 🔗 Links Importantes

- **Kommo:** https://garciaangie925.kommo.com
- **N8N:** https://n8n.io
- **Telegram Bots:** @BotFather (setup)
- **GitHub:** https://github.com/Paol10

---

## 📝 Notas Importantes

- ⚠️ **API Keys**: Guardar en `.env.local` (NO commitear)
- ⚠️ **Datos sensibles**: Nunca en repos públicas
- ✅ **Backups**: Hacer backup de Kommo cada semana
- ✅ **Docs**: Mantener actualizado este README

---

## 👤 Contacto

Paola García - garciaangie925@gmail.com

Creado con ❤️ usando Claude AI + Anthropic SDK
