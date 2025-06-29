# 🛠️ Troubleshooting Avanzado

## 🔧 Problemas del Panel de Monitoreo

### 🖥️ Panel No Responde

#### 🔍 Diagnóstico Paso a Paso
1. **🌐 Verificar Conectividad**
   ```bash
   ping monitoring.cineplanet.com.pe
   # Respuesta esperada: < 50ms
   ```

2. **🔐 Verificar Autenticación**
   - Cerrar sesión completamente
   - Limpiar cookies: `Ctrl + Shift + Del`
   - Reintentar login con 2FA

3. **🧹 Limpiar Caché del Navegador**
   ```
   Chrome: Ctrl + Shift + Del
   Firefox: Ctrl + Shift + Del
   Edge: Ctrl + Shift + Del
   ```

4. **📱 Verificar WebSocket**
   - F12 → Console
   - Buscar errores de WebSocket
   - Debe mostrar: "WebSocket connection established"

#### 🔧 Soluciones por Navegador

##### 🟢 Chrome
```
1. chrome://settings/privacy
2. Borrar datos de navegación
3. Deshabilitar extensiones temporalmente
4. Probar en modo incógnito
```

##### 🟢 Firefox
```
1. about:preferences#privacy
2. Limpiar datos y historial
3. Deshabilitar add-ons
4. Probar en ventana privada
```

##### 🟢 Edge
```
1. edge://settings/privacy
2. Elegir qué borrar
3. Reiniciar navegador
4. Probar en InPrivate
```

---

### 📊 Datos No Actualizan

#### 🔍 Síntomas
- Timestamps congelados
- Métricas estáticas
- Feed de transacciones detenido

#### 🔧 Soluciones Técnicas

##### 📱 Verificar Estado de WebSocket
```javascript
// En console del navegador (F12)
console.log(websocket.readyState);
// 0: Conectando
// 1: Abierto ✅
// 2: Cerrando
// 3: Cerrado ❌
```

##### 🔄 Forzar Reconexión
1. **Método 1:** `Ctrl + F5` (recarga completa)
2. **Método 2:** Cerrar y reabrir pestaña
3. **Método 3:** Logout y login nuevamente

##### 📡 Verificar Conectividad API
```bash
# En terminal (si tienes acceso)
curl -H "Authorization: Bearer [token]" \
https://api.cineplanet.com.pe/monitoring/status
```

#### 📞 Escalamiento
Si persiste > 5 minutos:
1. **📧 it-support@cineplanet.com.pe**
2. **📱 Soporte ext. 2500**
3. **🎫 Ticket con prioridad alta**

---

### 🚨 Alertas No Funcionan

#### 🔍 Diagnóstico
1. **🔊 Verificar Configuración de Audio**
   - Navegador permite notificaciones
   - Volumen del sistema > 50%
   - No hay otras apps bloqueando audio

2. **🔧 Verificar Filtros de Alertas**
   - Panel → Configuración → Alertas
   - Verificar que todos los tipos estén habilitados
   - Revisar umbrales configurados

3. **📱 Verificar Permisos del Navegador**
   ```
   Chrome: chrome://settings/content/notifications
   Firefox: about:preferences#privacy → Permissions
   Edge: edge://settings/content/notifications
   ```

#### 🔧 Soluciones
1. **🔄 Restablecer Configuración de Alertas**
2. **🔊 Probar Alerta Manual** (botón de prueba)
3. **📱 Verificar en Otro Navegador**
4. **📞 Contactar Administrador** si persiste

---

## 🖥️ Problemas de Rendimiento

### 🐌 Panel Lento

#### 🔍 Causas Comunes
- **🖥️ Hardware insuficiente** (RAM < 8GB)
- **🌐 Conexión lenta** (< 10 Mbps)
- **🔄 Múltiples pestañas** abiertas
- **📊 Período de alta actividad** (17:00-20:00)

#### 🔧 Optimizaciones
1. **💻 Optimización del Sistema**
   ```
   - Cerrar aplicaciones innecesarias
   - Liberar RAM (mínimo 4GB disponible)
   - Usar SSD si está disponible
   ```

2. **🌐 Optimización de Red**
   ```
   - Usar conexión cableada vs WiFi
   - Verificar ancho de banda: speedtest.net
   - Evitar descargas simultáneas
   ```

3. **🧹 Optimización del Navegador**
   ```
   - Máximo 5 pestañas abiertas
   - Deshabilitar extensiones no esenciales
   - Usar modo de alto rendimiento
   ```

### 📊 Gráficos No Cargan

#### 🔍 Posibles Causas
- **🚫 JavaScript deshabilitado**
- **🔒 Bloqueador de contenido**
- **📊 Problema con librería de gráficos**

#### 🔧 Soluciones
1. **✅ Habilitar JavaScript**
2. **🔓 Deshabilitar bloqueadores temporalmente**
3. **🔄 Refrescar página completamente**
4. **📱 Probar en modo incógnito**

---

## 🔐 Problemas de Autenticación

### 🚫 No Puede Iniciar Sesión

#### 🔍 Escenarios Comunes

##### 🔑 Credenciales Incorrectas
```
✅ Verificar usuario: [usuario]@cineplanet.com.pe
✅ Verificar contraseña (sin espacios)
✅ Verificar Caps Lock
✅ Probar con teclado en pantalla
```

##### 📱 Problemas con 2FA
```
🕐 Verificar hora del dispositivo
🔄 Regenerar código (esperar 30s)
📱 Verificar app Authenticator
🆘 Usar códigos de backup
```

##### 🔒 Cuenta Bloqueada
```
⏰ Esperar 15 minutos
📞 Contactar IT: ext. 2100
📧 unlock-account@cineplanet.com.pe
```

### 🕐 Sesión Expira Constantemente

#### 🔍 Causas
- **🍪 Cookies deshabilitadas**
- **🔒 Configuración de seguridad muy alta**
- **⏰ Reloj del sistema desincronizado**

#### 🔧 Soluciones
1. **🍪 Habilitar Cookies**
   ```
   Chrome: Configuración → Privacidad → Cookies
   Permitir para cineplanet.com.pe
   ```

2. **⏰ Sincronizar Reloj**
   ```
   Windows: time.windows.com
   Mac: Preferencias → Fecha y Hora
   Linux: ntpdate -s time.nist.gov
   ```

---

## 📱 Problemas Específicos por Dispositivo

### 💻 Escritorio

#### 🖥️ Resolución Mínima
- **Requerida:** 1920x1080
- **Recomendada:** 2560x1440
- **Múltiples monitores:** Usar principal para panel

#### ⌨️ Atajos de Teclado
```
F5: Refrescar panel
F11: Pantalla completa
Ctrl + 0: Zoom 100%
Ctrl + Shift + I: Herramientas de desarrollo
```

### 📱 Tablet (Uso Limitado)

#### 🎯 Funcionalidades Disponibles
- ✅ **Visualización de métricas**
- ✅ **Alertas básicas**
- ❌ **Configuración avanzada**
- ❌ **Análisis detallado**

#### 🔧 Configuración Recomendada
```
Orientación: Horizontal
Zoom: 80-90%
Navegador: Chrome/Safari
Conexión: WiFi estable
```

---

## 📞 Contacto por Tipo de Problema

### ⚡ Problemas Críticos (< 2 min)
```
📞 Soporte Urgente: ext. 2500
💬 Slack: #ops-emergency
📧 ops-emergency@cineplanet.com.pe
```

### 🔧 Problemas Técnicos (< 30 min)
```
📞 IT Support: ext. 2100
🎫 Helpdesk: helpdesk.cineplanet.com.pe
📧 it-support@cineplanet.com.pe
```

### 📚 Consultas de Uso (< 2 horas)
```
📚 Knowledge Base: kb.cineplanet.com.pe
💬 Slack: #monitoring-help
📧 training@cineplanet.com.pe
```

---

## 📋 Checklist de Troubleshooting

### ✅ Antes de Contactar Soporte
- [ ] **🔄 Intenté refrescar la página**
- [ ] **🌐 Verifiqué conexión a internet**
- [ ] **📱 Probé en modo incógnito**
- [ ] **🧹 Limpié caché del navegador**
- [ ] **⏰ Documenté hora exacta del problema**
- [ ] **📸 Tomé screenshot del error**

### ✅ Información para el Reporte
- [ ] **👤 Usuario afectado**
- [ ] **⏰ Timestamp del incidente**
- [ ] **🌐 Navegador y versión**
- [ ] **🖥️ Sistema operativo**
- [ ] **📝 Pasos exactos para reproducir**
- [ ] **🔍 Mensajes de error específicos**

---

**💡 Regla de Oro del Troubleshooting:** Si el problema persiste > 5 minutos y afecta el monitoreo, ESCALA INMEDIATAMENTE. La continuidad del servicio es prioritaria.
