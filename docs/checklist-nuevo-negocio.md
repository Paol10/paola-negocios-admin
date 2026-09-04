# Checklist: Onboarding Nuevo Negocio

**Cuando:** Se agrega un nuevo cliente/negocio  
**Responsable:** Paola + Erik  
**Tiempo estimado:** 4-6 horas

---

## 📋 Pre-Setup (Antes de empezar)

- [ ] Obtener datos del cliente:
  - [ ] Nombre del negocio
  - [ ] Tipo de negocio (servicios, productos, etc.)
  - [ ] Email de contacto
  - [ ] Teléfono/WhatsApp
  - [ ] Ubicación geográfica
  - [ ] Presupuesto mensual aproximado

- [ ] Definir alcance:
  - [ ] ¿Necesita página web? (1, 5, 10 páginas)
  - [ ] ¿Necesita CRM? (Kommo)
  - [ ] ¿Necesita automatización? (N8N)
  - [ ] ¿Necesita bot Telegram?
  - [ ] ¿Necesita videos automáticos?

---

## 🏗️ Setup Kommo

- [ ] Crear cuenta de cliente en Kommo
- [ ] Crear Pipeline personalizado:
  - [ ] Definir stages (cotización → pago → entrega → cierre)
  - [ ] Agregar campos personalizados (budget, fecha entrega, etc.)
  - [ ] Configurar usuarios/permisos

- [ ] Documentar:
  - [ ] Crear `docs/[negocio]-kommo.md`
  - [ ] Listar stages y campos
  - [ ] Agregar usuarios/credenciales (en `.env.local`)

---

## 🤖 Setup N8N

- [ ] Crear webhook para formulario cliente (si aplica)
- [ ] Crear HTTP Request a Kommo API
- [ ] Crear workflow de follow-up automático (opcional)
- [ ] Testing del workflow

- [ ] Documentar:
  - [ ] Copiar template de workflow
  - [ ] Editar: `n8n/workflows-[negocio]/`
  - [ ] Documenting: `n8n/workflows-[negocio]/README.md`

---

## 🤖 Setup Bots Telegram

- [ ] Crear bot en @BotFather
- [ ] Obtener token
- [ ] Conectar a N8N (si automatizar)
- [ ] Documentar: `bots-telegram/[bot-nombre]/README.md`

---

## 📁 Estructura de Carpetas Creada

```bash
# Crear en repo:
mkdir -p [negocio]/
mkdir -p kommo/[negocio]/
mkdir -p n8n/workflows-[negocio]/
```

---

## 📄 Archivos a Crear

- [ ] `[negocio]/instrucciones.md` (copia de monarca/instrucciones.md)
- [ ] `[negocio]/clientes.md` (lista de clientes)
- [ ] `[negocio]/checklist-diario.md` (tareas recurrentes)
- [ ] `kommo/[negocio]-pipeline.json` (exportar de Kommo)
- [ ] `n8n/workflows-[negocio]/webhook.json` (workflow webhook)
- [ ] `n8n/workflows-[negocio]/README.md` (documentación)

---

## 🔐 Variables de Entorno

Agregar a `.env.local`:

```env
# [NEGOCIO]
[NEGOCIO]_KOMMO_API_KEY=<key>
[NEGOCIO]_KOMMO_DOMAIN=<domain>.kommo.com
[NEGOCIO]_N8N_WEBHOOK_URL=<url>
[NEGOCIO]_TELEGRAM_BOT_TOKEN=<token>
```

---

## ✅ Testing

- [ ] Crear lead test en Kommo (manual)
- [ ] Probar webhook con curl
- [ ] Verificar que lead llegue a Kommo
- [ ] Probar notificaciones (Slack/email/Telegram)
- [ ] Verificar follow-ups automáticos

---

## 🚀 Go Live

- [ ] Conectar formulario del cliente a webhook
- [ ] Hacer prueba real con cliente
- [ ] Confirmar que todo funciona
- [ ] Activar automáticamente (cron jobs, etc.)
- [ ] Agregar a producción

---

## 📋 Documentación Final

- [ ] Readme de negocio actualizado
- [ ] Instrucciones claras en español
- [ ] Checklist diario disponible
- [ ] Contactos documentados
- [ ] Problemas resueltos documentados

---

## 📊 Post-Setup (Después de 30 días)

- [ ] Analizar pipeline: tasa de conversión
- [ ] Revisar leads: cuáles se convirtieron
- [ ] Optimizar mensajes de follow-up
- [ ] Ajustar campos Kommo si es necesario
- [ ] Hacer reporte a cliente

---

**Plantilla creada:** 2026-09-04  
**Última actualización:** 2026-09-04
