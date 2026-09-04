# Migración: De Belate Parfum a Paola Negocios Admin

**Fecha:** 2026-09-04  
**Status:** ✅ FASE 1 COMPLETADA

---

## 📊 Resumen

Se ha creado una **repo central de operaciones** (`paola-negocios-admin`) para administrar múltiples negocios sin mezclar con Belate Parfum.

### ¿Qué se migró?

✅ **Documentación completa:**
- Instrucciones de Monarca Cocinas
- Configuración Kommo (CRM)
- Workflows N8N (automatización)
- Checklist para nuevos negocios
- Procesos operativos

✅ **Estructura lista para:**
- Múltiples negocios (Monarca, Voy a Vender, otros)
- Múltiples bots Telegram
- Scripts de automatización compartidos
- Documentación centralizada

---

## 🔗 URLs Importantes

**GitHub Central Repo:**  
https://github.com/Paol10/paola-negocios-admin

**Belate Parfum** (SEPARADO):  
https://github.com/Paol10/belate-parfum

---

## 📁 Próximas Repos (Paso 2 & 3)

### OPCIÓN A: Crear repos individuales por sitio web

```
✅ Repo Central:      paola-negocios-admin
├── monarca-cocinas-web         (sitio web Monarca)
├── voy-a-vender-colombia       (landing page + servicios)
└── [otros-negocios]            (cuando se agreguen)
```

### OPCIÓN B: Mantener la estructura actual

Esperar a que Erik proporcione las credenciales de `voyavender-conia` (repo existente de Voy a Vender).

---

## 📋 Tareas Pendientes

### INMEDIATO (Hoy/Mañana)

- [ ] Esperar credenciales GitHub de Erik
  - [ ] Repo de Monarca (`monarca-cocinas-web`)
  - [ ] Repo de Voy a Vender (`voyavender-conia` o similar)

- [ ] Crear `.env.local` localmente con:
  ```
  MONARCA_KOMMO_API_KEY=<obtener de Kommo>
  MONARCA_KOMMO_DOMAIN=garciaangie925.kommo.com
  ```

- [ ] Obtener Kommo API Key (BLOQUEADOR para N8N)
  - Ir a: https://garciaangie925.kommo.com/settings/
  - Buscar: "API REST" o "Developer"
  - Copiar API Key

### CORTO PLAZO (Esta semana)

- [ ] Completar N8N workflow (Monarca → Kommo)
  - [ ] Agregar API Key
  - [ ] Testing del webhook
  - [ ] Conectar formulario de Monarca

- [ ] Crear repos individuales para sitios web
  - `monarca-cocinas-web` (Next.js)
  - `voy-a-vender-colombia` (Next.js o Next.js)
  - Referencia a `paola-negocios-admin` en docs

- [ ] Crear contenido Facebook para Voy a Vender

### MEDIANO PLAZO (Próximas 2 semanas)

- [ ] Hacer paquetes personalizados de Voy a Vender
  - Basados en aprendizaje de N8N + Kommo

- [ ] Crear estrategia de landing page Colombia
  - Tropicalizar o página nueva

- [ ] Setup de segundo negocio (cuando llegue)
  - Usar checklist-nuevo-negocio.md

---

## 🚀 FASE 2: Crear Repos de Sitios Web

**Cuando:** Una vez recibas credenciales de Erik

**Repos a crear:**

### 1. monarca-cocinas-web
```bash
cd ~/Desktop
mkdir monarca-cocinas-web
cd monarca-cocinas-web
# Clonar del repo de Erik o crear nuevo
git init
# Estructura: Next.js + conexión a paola-negocios-admin
```

**Referencia en README:**
```markdown
# Configuración

Ver instrucciones de operación en:
📖 ../paola-negocios-admin/monarca/instrucciones.md
🤖 ../paola-negocios-admin/n8n/workflows-monarca/
💾 ../paola-negocios-admin/kommo/README.md
```

### 2. voy-a-vender-colombia
```bash
cd ~/Desktop
mkdir voy-a-vender-colombia
cd voy-a-vender-colombia
# Clonar o crear nuevo basado en voyavender-conia
```

**Próximas acciones:** (Ver sección de Voy a Vender)

---

## 🎯 FASE 3: Contenido y Paquetes

### A. Tus 3 Paquetes de Voy a Vender

Basados en análisis de voyavender-conia-web.vercel.app:

**Paquete 1: Arranque** ($2,490/mes)
- Recepcionista WhatsApp IA
- 1 página web
- Panel de leads

**Paquete 2: Motor** ($5,490/mes)  ← MÁS POPULAR
- Todo de Arranque
- Hasta 5 páginas web
- 12 videos verticales + 20 gráficos/mes
- Publicación automática Facebook/Instagram
- Follow-up automático leads

**Paquete 3: Piloto** ($9,900/mes)
- Todo de Motor
- Reactivación de base de clientes
- SEO activo con contenido
- Sesión estratégica mensual (45 min)

### B. Adaptaciones Colombia

- Precios: $2,490 → ~$9,960 COP
- Ciudades: CDMX → Bogotá, Medellín, Cali
- Moneda: USD → COP
- Legales: Mexicanas → Colombianas

---

## 📊 Status Actual

| Componente | Status | Bloqueador | Acción |
|-----------|--------|-----------|--------|
| Repo central | ✅ | - | Listo |
| Monarca Kommo | ✅ | - | Listo |
| N8N workflow | 🟡 | API Key Kommo | Esperar |
| Paquetes Voy a Vender | 🟡 | Credenciales Erik | Esperar |
| Contenido Facebook | ⏳ | Paquetes definidos | Próximo |
| Sitios web | ⏳ | Credenciales Erik | Próximo |

---

## 🔐 Credenciales Necesarias

⚠️ Crear archivo `.env.local` (NO COMMITEAR) con:

```env
# De Erik:
MONARCA_ADMIN_USER=erik@monarcacocinas.com
MONARCA_ADMIN_PASS=Erik1989*

# De Kommo:
MONARCA_KOMMO_API_KEY=<obtener de settings>

# De N8N:
N8N_WEBHOOK_URL=<tu instancia N8N>

# De GitHub (opcional):
GITHUB_MONARCA_REPO=<URL repo Monarca>
GITHUB_VENDER_REPO=<URL repo Voy a Vender>
```

---

## 📞 Próximas Acciones

1. **Hoy/Mañana:** 
   - Esperar credenciales de Erik
   - Obtener Kommo API Key
   - Empezar paquetes de Voy a Vender

2. **Esta semana:**
   - Completar N8N → Kommo
   - Crear repos sitios web
   - Contenido Facebook

3. **Próximas 2 semanas:**
   - Lanzar estrategia Colombia
   - Setup segundo negocio (si aplica)

---

## 📚 Links Útiles

**Este repo:**
- https://github.com/Paol10/paola-negocios-admin

**Externo:**
- Kommo: https://garciaangie925.kommo.com
- N8N: https://n8n.io
- Monarca web: https://monarcacocinas.com

---

**Creado:** 2026-09-04  
**Próxima revisión:** 2026-09-11

¡¡MUY BIEN Paola!! 🎉 Migración lista. Espera credenciales de Erik para siguiente fase.
