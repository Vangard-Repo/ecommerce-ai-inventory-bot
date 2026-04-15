🛒 Omnichannel Multimodal AI Sales Agent (n8n + Qdrant + WooCommerce)

![alt text](https://raw.githubusercontent.com/Vangard-Repo/ecommerce-ai-inventory-bot/main/ai-ecommerce-omnicanal-sales-agent.PNG)


🚀 Sobre este Proyecto
Este repositorio contiene la arquitectura de un Agente de Ventas de IA de Nivel Empresarial. No es un simple chatbot de preguntas y respuestas; es un asistente conversacional avanzado capaz de ver, escuchar y gestionar el inventario de un E-Commerce en tiempo real.
Diseñado para tiendas online, retailers y marcas que reciben un alto volumen de consultas por WhatsApp e Instagram y necesitan automatizar su atención al cliente sin perder el toque humano ni dejar escapar ventas por falta de stock.

📺 Mira la demostración en video de este sistema funcionando aquí

🧠 Características Principales (Multimodal & RAG)
Este sistema orquesta un flujo de datos complejo utilizando LangChain dentro de n8n:

🎙️👁️ Soporte Multimodal (Texto, Audio e Imágenes):
Notas de Voz: Integración con Naga API (Whisper v3 Turbo) para transcribir audios de WhatsApp al instante.
Imágenes: Integración con Google Gemini 2.5 Flash Vision para analizar fotos enviadas por los clientes (ej. "¿Tienen esta camisa en talla M?").

🚦 Encolamiento Seguro (Redis): Sistema de colas de mensajes mediante Redis para procesar ráfagas de chats sin perder contexto ni colapsar los Webhooks.

🧠 Memoria Persistente (PostgreSQL): El agente recuerda el contexto de la conversación a través de sesiones almacenadas en base de datos.

📦 Ruteo de Intenciones y RAG:
BuscadorProductos: Consulta el stock, precios y links directamente de la base de datos de la tienda.
BuscadorFAQs (Qdrant): Motor de búsqueda vectorial que responde políticas de envío, devoluciones y métodos de pago basándose estrictamente en el conocimiento de la empresa.

📈 Recuperador de Ventas Perdidas: Si un producto tiene stock_status = outofstock, el agente activa un protocolo de retención, ofreciendo congelar el precio y registrando los datos del cliente en Google Sheets para notificarle cuando vuelva a estar disponible.

🛠️ Stack Tecnológico Utilizado
Orquestador: n8n (Self-hosted)
Plataforma Omnicanal: Chatwoot (Conectado a WhatsApp Cloud API / Evolution API)
Modelos AI: DeepSeek (Agente Principal), GPT-4o-mini (Verificador/Formateador), Gemini 2.5 Flash (Vision), Whisper (Audio)
Vector Database: Qdrant (Retrieval-Augmented Generation)
Memoria & Caché: PostgreSQL & Redis
Data Management: Integración con ERP/WooCommerce y Google Sheets

⚠️ Nota de Seguridad
El archivo .json alojado en este repositorio está sanitizado. Todas las credenciales, URLs de Webhooks, APIs de Chatwoot, Qdrant y bases de datos han sido eliminadas para proteger la infraestructura del servidor.
Este flujo requiere configuración de hardware (VPS), despliegue de bases de datos vectoriales y conexión a APIs de LLMs de terceros. No es un template básico.

💼 Lleva tu E-Commerce al siguiente nivel
¿Tienes una tienda online y tu equipo no da abasto respondiendo mensajes en WhatsApp? Yo construyo la infraestructura que tu negocio necesita para vender en piloto automático 24/7.

🌐 Visita mi web y conoce mis servicios:vangard-ai.com

📩 O contrátame a través de Workana: Mi Perfil de Workana
