# Kommo (CRM) - Guía Centralizada

**CRM:** Kommo (formerly AmoCRM)  
**URL:** https://garciaangie925.kommo.com  
**Idioma:** Español  
**Timezone:** América/Ciudad de México

---

## 🎯 Configuración por Negocio

### Monarca Cocinas Integrales

**Pipeline:** "Monarca - Cocinas Integrales"

**Stages:**
1. Cotización pendiente
2. Anticipo pagado
3. Fabricación
4. Entregado
5. Cerrado

**Campos personalizados:**
- Tipo de proyecto (Modular/A medida/Reforma)
- Budget
- Fecha entrega requerida
- Estado de fabricación
- Material principal (Madera/Acrílico/Vidrio)

**Usuarios:**
- Erik (Propietario)
- Paola (Admin)

---

## 📊 Datos Actuales

### Pipeline Overview

| Etapa | Cantidad | Acciones |
|-------|----------|----------|
| Cotización pendiente | 1 | Arq. René (seguimiento) |
| Anticipo pagado | 1 | Familia López (en fabricación) |
| Fabricación | 1 | Familia López |
| Entregado | 0 | - |
| Cerrado | 0 | - |

### Leads Detalles

**Lead 1: Arq. René Ayala**
- Email: (en Kommo)
- Teléfono: (en Kommo)
- Proyecto: Cocina modular gris
- Stage: Cotización pendiente
- Acción: Enviado presupuesto, esperando respuesta
- Última interacción: [fecha]

**Lead 2: Familia López**
- Email: (en Kommo)
- Teléfono: (en Kommo)
- Proyecto: Cocina a medida
- Stage: Fabricación
- Acción: URGENTE - Delivery vencida
- Última interacción: [fecha]

---

## 🔧 Integraciones

### N8N → Kommo
**Estado:** En configuración

**Endpoint:** `https://garciaangie925.kommo.com/api/v2/leads`

**Flujo:**
1. Webhook recibe formulario desde Monarca website
2. N8N HTTP Request crea lead en Kommo
3. Lead asignado a "Cotización pendiente"
4. Notificación a Erik

**Pendiente:** API Key authentication

---

## 📋 Tareas Recurrentes

### Diario
- [ ] Revisar nuevos leads en Kommo
- [ ] Responder mensajes de clientes
- [ ] Actualizar status de proyectos en fabricación

### Semanal
- [ ] Backup de Kommo (exportar leads)
- [ ] Revisar pipeline: conversión rates
- [ ] Contactar clientes en "Cotización" sin respuesta

### Mensual
- [ ] Reporte de ventas a Erik
- [ ] Análisis de márgenes por proyecto
- [ ] Revisar y ajustar campos personalizados

---

## 🔐 API Key

⚠️ **GUARDAR EN `.env.local` (NO commitear)**

```
KOMMO_API_KEY=<obtener de Kommo settings>
KOMMO_DOMAIN=garciaangie925.kommo.com
```

**Cómo obtener:**
1. Ir a: https://garciaangie925.kommo.com/settings/
2. Buscar: "API REST" o "Developer"
3. Generar/copiar API Key

---

## 📚 Recursos

- Docs Kommo: https://documentation.kommo.com/
- API Reference: https://documentation.kommo.com/api/
- Guía campos custom: [link a campos-personalizados.md]

---

**Última actualización:** 2026-09-04
