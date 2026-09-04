# N8N - Workflows de Automatización

**Plataforma:** N8N (Open source workflow automation)  
**URL:** https://n8n.io  
**Instancia:** [Tu instancia N8N - URL/detalles]

---

## 📊 Workflows Activos

### 1. Monarca: Formulario → Kommo

**Nombre:** `monarca-webhook-to-kommo`  
**Status:** 🟡 En configuración (esperando API Key Kommo)  
**Trigger:** Webhook POST desde formulario Monarca  
**Output:** Lead creado en Kommo

**Nodos:**
1. **Webhook** (POST)
   - URL: `https://n8n.io/webhook/monarca-forms`
   - Acepta: nombre, email, teléfono, proyecto, budget

2. **HTTP Request** (Kommo API)
   - Method: POST
   - URL: `https://garciaangie925.kommo.com/api/v2/leads`
   - Headers: Authorization: Bearer [API_KEY]
   - Body: Mapeo de campos

3. **Notificación** (Optional)
   - Slack/Email a Erik con nuevo lead

**Campos mapeados:**
```
Webhook → Kommo
nombre → name
email → email
teléfono → phone
proyecto → description
budget → custom_field_budget
```

**Próximos pasos:**
- [ ] Obtener Kommo API Key
- [ ] Completar Authorization header
- [ ] Testing con webhook real
- [ ] Activar en producción
- [ ] Conectar formulario Monarca

**Archivo:** `workflows-monarca/webhook-formulario.json`

---

### 2. Monarca: Follow-up Leads Fríos

**Nombre:** `monarca-followup-leads`  
**Status:** 🔴 No iniciado  
**Trigger:** Cron cada 3 días  
**Output:** Mensaje WhatsApp a clientes sin respuesta

**Concepto:**
- Buscar leads en "Cotización pendiente" sin interacción en 3 días
- Enviar recordatorio por WhatsApp
- 3 intentos antes de marcar como "Lead frío"

**Archivo:** `workflows-monarca/followup-leads.json` (plantilla)

---

## 📁 Estructura de Workflows

```
n8n/
├── workflows-monarca/
│   ├── webhook-formulario.json          # Formulario → Kommo
│   ├── followup-leads.json              # Recordatorios automáticos
│   └── README-monarca.md                # Documentación específica
│
├── workflows-compartidos/
│   ├── send-whatsapp-message.json       # Template: enviar WhatsApp
│   ├── send-email.json                  # Template: enviar email
│   ├── log-to-sheets.json               # Template: logging a Google Sheets
│   └── README-compartidos.md            # Documentación
│
└── README.md (este archivo)
```

---

## 🚀 Quick Start

### Para Monarca

1. **Ver configuración webhook actual:**
   ```bash
   cat workflows-monarca/webhook-formulario.json
   ```

2. **Próximos pasos:**
   - Obtener Kommo API Key
   - Editar archivo JSON con auth header
   - Deploy a N8N
   - Testing

### Para otros negocios

1. **Copiar workflow compartido:**
   ```bash
   cp workflows-compartidos/send-whatsapp-message.json \
      workflows-[nuevo-negocio]/send-whatsapp.json
   ```

2. **Adaptar variables:**
   - Cambiar IDs de negocio
   - Actualizar URLs de APIs
   - Customizar mensajes

---

## 🔧 Integrations Disponibles

### Webhook (Trigger)
- Monarca formulario → Crear lead Kommo
- Otros formularios → Cualquier acción

### HTTP Request (Cualquier API)
- Kommo REST API ✅
- WhatsApp API (próximo)
- Google Sheets (logging) ✅

### Slack (Notificaciones)
- Alertas de nuevos leads
- Errores de workflows

### Google Sheets (Logging/Backup)
- Guardar historial de leads
- Respaldos automáticos

---

## 📝 Variables de Entorno

⚠️ **Guardar en `.env` (NO commitear)**

```env
# Kommo
KOMMO_API_KEY=<API Key>
KOMMO_DOMAIN=garciaangie925.kommo.com

# N8N
N8N_WEBHOOK_URL=<Tu URL N8N>

# Otras APIs
WHATSAPP_API_KEY=<Si aplica>
SLACK_WEBHOOK=<Si aplica>
```

---

## 🧪 Testing

### Test Webhook Monarca

```bash
curl -X POST http://localhost:5678/webhook/monarca-forms \
  -H "Content-Type: application/json" \
  -d '{
    "nombre": "Test Cliente",
    "email": "test@example.com",
    "telefono": "+52 123 456 7890",
    "proyecto": "Cocina modular",
    "budget": "$10,000"
  }'
```

### Resultado esperado:
- Lead creado en Kommo ✅
- Stage: "Cotización pendiente" ✅
- Email de notificación a Erik ✅

---

## 📚 Recursos

- N8N Docs: https://docs.n8n.io/
- N8N Workflows: https://n8n.io/workflows/
- Kommo API Docs: https://documentation.kommo.com/api/

---

## 🤝 Pasos Siguientes

1. **Monarca Webhook:** Completar API Key → Deploy
2. **Follow-up automático:** Crear workflow recordatorios
3. **Multi-negocio:** Duplicar workflows para nuevos clientes
4. **Alertas:** Integrar Slack para notificaciones

---

**Última actualización:** 2026-09-04  
**Próximo review:** 2026-09-18
