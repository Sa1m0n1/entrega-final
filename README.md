# entrega-final
# Automatización de Correos con LLM (Catering)

## Descripción

Sistema automatizado que procesa correos entrantes en Gmail, clasifica la intención del cliente mediante modelos LLM y envía respuestas automáticas personalizadas.

---

## Requisitos

* Cuenta en plataforma (n8n / Make)
* Cuenta de Gmail conectada
* API Key de LLM (OpenAI / Groq)
* Google Sheets (opcional)

---

## Importación del workflow

1. Descargar archivo del workflow (.json)
2. Abrir n8n / Make
3. Seleccionar:

   * "Import workflow"
4. Subir archivo
5. Guardar

---

## Configuración

### 1. Gmail Trigger

* Conectar cuenta Gmail
* Configurar:

  * Trigger: "New Email"
  * Frecuencia: cada 1 hora

---

### 2. LLM

Configurar credenciales:

* API Key
* Modelo

Verificar prompts:

* LLM 1 → clasificación
* LLM 2 → presupuesto
* LLM 3 → reuniones

---

### 3. Google Sheets (opcional)

1. Crear hoja
2. Conectar cuenta
3. Mapear campos:

   * correo
   * fecha
   * hora
   * mensaje

---

### 4. Email (Gmail)

* Configurar nodo "Send Email"
* Definir remitente

---

### Ejecución

1. Activar workflow
2. Enviar un correo de prueba
3. Esperar ejecución (máx 1 hora)
4. Verificar respuesta automática

---

## Pruebas reproducibles

### Caso 1: Presupuesto

Correo:
"Hola, necesito presupuesto para 50 personas para un cumpleaños"

Resultado esperado:

* Categoría: solicitud_presupuesto
* Respuesta con precio: 500000
* Email enviado

---

### Caso 2: Reunión

Correo:
"Podemos reunirnos el 25 de marzo a las 16hs?"

Resultado esperado:

* Categoría: agendar_reunion
* Fecha: "25 de marzo"
* Hora: "16:00"
* Registro en Google Sheets
* Email enviado

---

### Caso 3: Información

Correo:
"Quiero saber qué servicios ofrecen"

Resultado esperado:

* Categoría: solicitud_informacion
* Respuesta automática
* Email enviado

---

🛠️ Personalización

* Cambiar precio por persona en LLM 2
* Añadir nuevas categorías en SWITCH
* Modificar respuestas en SET

---

## 📄 Licencia

Uso educativo
