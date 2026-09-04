# Monarca Cocinas Integrales - Instrucciones Setup

**Negocio:** Diseño y fabricación de cocinas integrales  
**Ubicación:** Puerto Vallarta, Estado de México  
**Admin:** Erik + Paola  
**Credenciales:** erik@monarcacocinas.com / Erik1989*

---

## ✅ SETUP COMPLETADO

### 1. Kommo (CRM)
- ✅ Cuenta creada: garciaangie925.kommo.com
- ✅ Pipeline creado: "Monarca - Cocinas Integrales"
- ✅ Stages: Cotización pendiente → Anticipo pagado → Fabricación → Entregado → Cerrado

### 2. Kommo Pipeline - Etapas

| Etapa | Descripción | Acción |
|-------|-------------|--------|
| **Cotización pendiente** | Cliente nuevo, requiere presupuesto | Crear cotización automática |
| **Anticipo pagado** | Cliente pagó adelanto (50%) | Iniciar producción |
| **Fabricación** | Cocina en construcción | Tracking de progreso |
| **Entregado** | Cocina instalada en cliente | Confirmar satisfacción |
| **Cerrado** | Proyecto finalizado | Archivar lead |

### 3. Clientes Agregados

#### Cliente 1: Familia López (vencido/overdue)
- **Estado:** Fabricación (vencida)
- **Proyecto:** Cocina modular gris
- **Problema:** Delivery vencida - Contactar Erik sobre estado real
- **Acción pendiente:** Confirmar si se entregó o hay retraso

#### Cliente 2: Arq. René Ayala
- **Estado:** Cotización sin anticipo
- **Proyecto:** Cocina a medida (proyecto arq.)
- **Problema:** Cliente tiene cotización pero NO ha pagado anticipo
- **Acción:** Seguimiento de venta

---

## 🤖 N8N Workflows

### Workflow: Webhook → Kommo (EN CONFIGURACIÓN)

**Estado:** Esperando API Key de Kommo

**Flujo:**
1. Webhook recibe datos del formulario Monarca
2. HTTP Request a: `https://garciaangie925.kommo.com/api/v2/leads`
3. Crea lead automáticamente en Kommo
4. Asigna a pipeline "Monarca - Cocinas Integrales"
5. Stage inicial: "Cotización pendiente"

**Datos que captura:**
- Nombre cliente
- Email
- Teléfono
- Descripción proyecto
- Budget aproximado

**Próximos pasos:**
- [ ] Obtener API Key de Kommo
- [ ] Configurar Authorization header en N8N
- [ ] Mapear campos webhook → Kommo
- [ ] Testing con datos reales
- [ ] Activar en producción

---

## 📋 Checklist Diario

### Mañana
- [ ] Revisar Kommo: nuevos leads
- [ ] Contactar clientes en "Cotización pendiente"
- [ ] Actualizar stage de proyectos en fabricación

### Semanal
- [ ] Backup de Kommo
- [ ] Revisar N8N: webhooks recibidos
- [ ] Reporte a Erik: estado de proyectos

### Mensual
- [ ] Analizar pipeline: tasa de conversión
- [ ] Optimizar mensajes de cotización
- [ ] Revisar precios y márgenes

---

## 🔧 Problemas Resueltos

### Problema 1: Kommo Pipeline Creation Error
**Síntoma:** "Algo salió mal" al crear pipeline customizado  
**Causa:** Kommo plan gratuito/starter tiene limitaciones  
**Solución:** Usar template preexistente (Online Store) + renombrar stages ✅  
**Status:** RESUELTO

### Problema 2: GitHub Credentials Expired
**Síntoma:** "La autenticación de GitHub CLI expiró"  
**Causa:** Token expirado  
**Comando:** `gh auth login` + seleccionar HTTPS + browser auth ✅  
**Status:** RESUELTO

### Problema 3: N8N → Kommo Integration
**Síntoma:** No hay connector nativo de Kommo en N8N  
**Solución:** Usar HTTP Request node + Kommo REST API ✅  
**Pendiente:** API Key authentication

---

## 📞 Contactos

- **Erik:** erik@monarcacocinas.com (dueño)
- **Familia López:** (ver Kommo)
- **Arq. René Ayala:** (ver Kommo)

---

## 🔐 Credenciales (⚠️ NO commitear)

Ver `.env.local`:
```
KOMMO_ACCOUNT=garciaangie925.kommo.com
KOMMO_EMAIL=erik@monarcacocinas.com
N8N_WEBHOOK_URL=https://n8n.io/...
```

---

**Última actualización:** 2026-09-04  
**Próxima revisión:** 2026-09-11
