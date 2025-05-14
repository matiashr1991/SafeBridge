# SafeBridge
SafeBridge
Sistema Preventivo de Grooming en Redes Domésticas y Educativas

Descripción del Proyecto / Introducción: SafeBridge es una solución de bajo costo y de implementación local que busca prevenir el acoso sexual a menores en entornos digitales (grooming) mediante el monitoreo inteligente del tráfico de red. El sistema está diseñado para correr en un entorno controlado, como una red doméstica o escolar, detectando patrones sospechosos en comunicaciones digitales, sin necesidad de invadir la privacidad del usuario mediante el acceso directo a sus dispositivos o redes sociales.
Definiciones del Proyecto:
Grooming: Estrategia de acoso en la que un adulto se gana la confianza de un menor en plataformas digitales con fines sexuales.
Proxy Local: Servidor que intermedia las conexiones de red y permite inspeccionar el tráfico.
MITMProxy: Proxy de código abierto que permite inspeccionar tráfico HTTPS mediante certificados personalizados.
MikroTik: Router configurable que permite redireccionar todo el tráfico de red hacia el proxy de análisis.
Definiciones del Sistema: SafeBridge se basa en una infraestructura de red compuesta por un router MikroTik que fuerza a todos los dispositivos a pasar su tráfico por un proxy local montado en una Raspberry Pi. Este proxy captura y analiza los paquetes utilizando patrones preentrenados de lenguaje y comportamiento para detectar grooming. Las alertas se notifican a los adultos responsables.
Requisitos:
Funcionales:
Monitorear tráfico HTTP/HTTPS de todos los dispositivos de la red local.
Detectar patrones sospechosos (mensajes, URLs, interacciones) relacionados con grooming.
Asociar tráfico a un dispositivo mediante su MAC address.
Emitir alertas a padres/tutores ante detección.
Generar registros de actividad anonimizados.
No funcionales:
Bajo costo de implementación.
Privacidad del usuario (no accede a cuentas personales).
Funcionamiento 24/7 con bajo consumo.
No necesita instalación en cada dispositivo.

Casos de Estudio:
Familia con hijos en edad escolar que navegan redes sociales desde distintos dispositivos.
Institución educativa que desea prevenir acoso digital dentro de su red Wi-Fi.
Cibercafés o centros comunitarios que ofrecen conectividad a niños y adolescentes.
Propuesta de Solución:
Propuesta Funcional:
Implementar un sistema de análisis del tráfico en tiempo real.
Clasificación de mensajes, URLs o metadatos para detección de interacciones inapropiadas.
Registro de dispositivos conectados mediante sus MACs.
Alertas automatizadas vía correo electrónico o interfaz local.
Propuesta Técnica:
Router MikroTik para redireccionamiento y firewall.
Raspberry Pi (o PC económica) con MITMProxy para inspección de tráfico HTTPS.
Certificado SSL autofirmado instalado en los dispositivos.
Backend con Python (Flask) para procesamiento, clasificación e interfaz.
Modelo de lenguaje básico (NLTK, scikit-learn o HuggingFace) entrenado para patrones de grooming.

SafeBridge
Sistema Preventivo de Grooming en Redes Domésticas y Educativas

Descripción del Proyecto / Introducción: SafeBridge es una solución de bajo costo y de implementación local que busca prevenir el acoso sexual a menores en entornos digitales (grooming) mediante el monitoreo inteligente del tráfico de red. El sistema está diseñado para correr en un entorno controlado, como una red doméstica o escolar, detectando patrones sospechosos en comunicaciones digitales, sin necesidad de invadir la privacidad del usuario mediante el acceso directo a sus dispositivos o redes sociales.
Definiciones del Proyecto:
Grooming: Estrategia de acoso en la que un adulto se gana la confianza de un menor en plataformas digitales con fines sexuales.
Proxy Local: Servidor que intermedia las conexiones de red y permite inspeccionar el tráfico.
MITMProxy: Proxy de código abierto que permite inspeccionar tráfico HTTPS mediante certificados personalizados.
MikroTik: Router configurable que permite redireccionar todo el tráfico de red hacia el proxy de análisis.
Definiciones del Sistema: SafeBridge se basa en una infraestructura de red compuesta por un router MikroTik que fuerza a todos los dispositivos a pasar su tráfico por un proxy local montado en una Raspberry Pi. Este proxy captura y analiza los paquetes utilizando patrones preentrenados de lenguaje y comportamiento para detectar grooming. Las alertas se notifican a los adultos responsables.
Requisitos:
Funcionales:
Monitorear tráfico HTTP/HTTPS de todos los dispositivos de la red local.
Detectar patrones sospechosos (mensajes, URLs, interacciones) relacionados con grooming.
Asociar tráfico a un dispositivo mediante su MAC address.
Emitir alertas a padres/tutores ante detección.
Generar registros de actividad anonimizados.
No funcionales:
Bajo costo de implementación.
Privacidad del usuario (no accede a cuentas personales).
Funcionamiento 24/7 con bajo consumo.
No necesita instalación en cada dispositivo.

Flujo Completo del Sistema

Casos de Estudio:
Familia con hijos en edad escolar que navegan redes sociales desde distintos dispositivos.
Institución educativa que desea prevenir acoso digital dentro de su red Wi-Fi.
Cibercafés o centros comunitarios que ofrecen conectividad a niños y adolescentes.
Propuesta de Solución:
Propuesta Funcional:
Implementar un sistema de análisis del tráfico en tiempo real.
Clasificación de mensajes, URLs o metadatos para detección de interacciones inapropiadas.
Registro de dispositivos conectados mediante sus MACs.
Alertas automatizadas vía correo electrónico o interfaz local.
Propuesta Técnica:
Router MikroTik para redireccionamiento y firewall.
Raspberry Pi (o PC económica) con MITMProxy para inspección de tráfico HTTPS.
Certificado SSL autofirmado instalado en los dispositivos.
Backend con Python (Flask) para procesamiento, clasificación e interfaz.
Modelo de lenguaje básico (NLTK, scikit-learn o HuggingFace) entrenado para patrones de grooming.


Casos de Uso
Caso de Uso 1: “Alerta por conversación sospechosa en red escolar”
Descripción:
Un alumno de una escuela se conecta a la red Wi-Fi institucional. Durante el recreo, chatea en una red social desde su celular. SafeBridge intercepta y analiza el contenido textual del tráfico, detectando patrones que coinciden con grooming. El sistema notifica a los responsables a través de una alerta automatizada.
<a href="https://imgbb.com/"><img src="https://i.ibb.co/4nBmgTBN/casideuso1.jpg" alt="casideuso1" border="0"></a>

Flujo:
Alumno se conecta a la red escolar (pasando por MikroTik)


Su tráfico HTTPS es interceptado por el proxy local


El contenido textual es enviado al backend de análisis


El modelo NLP detecta una conversación sospechosa


Se genera una alerta con hora, dispositivo (MAC), y nivel de riesgo


El tutor recibe un mail con la información del evento



Caso de Uso 2: “Registro de actividad sospechosa recurrente en red doméstica”
Descripción:
Un niño usa una tablet conectada a la red Wi-Fi de su casa. A lo largo del día, el sistema detecta múltiples interacciones sospechosas distribuidas en varias sesiones. SafeBridge registra esta actividad en logs anonimizados y produce un informe resumido para su posterior revisión por parte de los padres.
<a href="https://imgbb.com/"><img src="https://i.ibb.co/YFTLJxxN/casodeuso2.jpg" alt="casodeuso2" border="0"></a>

Flujo:
El niño utiliza la tablet (juegos, mensajería, etc.)


Tráfico de la red es inspeccionado por el proxy


Se detectan múltiples eventos de riesgo bajo a medio


Se agregan al registro interno con metadata (MAC, hora, texto procesado)


Una vez por día, el sistema genera un resumen automático con:


Número de alertas


Palabras clave


Tiempos más activos


Los padres consultan el informe desde un panel web local

Caso de Uso 3: “Intento de eludir monitoreo desde un dispositivo nuevo”

Descripción:
Un adolescente conecta un nuevo dispositivo (smartphone) a la red escolar sin pasar por el certificado SSL requerido. SafeBridge detecta el intento de evasión (porque no puede inspeccionar su tráfico) y genera una alerta de “conexión no segura”. Esto permite a los administradores saber que alguien intenta evitar la inspección del tráfico.
<a href="https://imgbb.com/"><img src="https://i.ibb.co/SX1K9myn/casideuso3.jpg" alt="casideuso3" border="0"></a>
Flujo:
El adolescente conecta un dispositivo sin instalar el certificado SSL del proxy


El tráfico HTTPS no puede ser inspeccionado correctamente


MITMProxy identifica tráfico cifrado no interceptable (handshake fallido)


Se registra un evento de evasión con IP/MAC del dispositivo


Se emite una alerta de seguridad al panel/tutor


El administrador puede restringir la MAC o solicitar intervención



Modelo  de BD - NoSQL (MongoDB)

Modelo Conceptual General
La base de datos debe almacenar:
Dispositivos conectados (identificados por MAC).


Eventos de tráfico inspeccionados.


Alertas generadas por patrones de grooming o evasión.


Usuarios responsables (padres, administradores escolares).


Resúmenes periódicos (diarios/semanales).


Certificados SSL instalados / verificados.


Colecciones Principales en MongoDB
1. devices (Dispositivos Conectados)
{
  "_id": ObjectId,
  "mac_address": "00:1A:2B:3C:4D:5E",
  "ip_address": "192.168.0.102",
  "hostname": "tablet-niño",
  "first_seen": ISODate,
  "last_seen": ISODate,
  "trusted": true,
  "ssl_cert_installed": true,
  "user_type": "alumno" // o "desconocido" // “padre” // “hijo/a”
}


2. traffic_logs (Registro de Tráfico Analizado)
{
  "_id": ObjectId,
  "timestamp": ISODate,
  "mac_address": "00:1A:2B:3C:4D:5E",
  "content_type": "text/html",
  "url": "https://example.com/chat",
  "text_snippet": "Hola, ¿cuántos años tienes?",
  "risk_level": "medio",
  "keywords_detected": ["años", "edad", "privado"],
  "session_id": "sess-78ba9f2",
  "is_suspicious": true
}
3. alerts (Alertas Detectadas)
{
  "_id": ObjectId,
  "mac_address": "00:1A:2B:3C:4D:5E",
  "timestamp": ISODate,
  "alert_type": "grooming_detectado", // o "evasión", "tráfico_sospechoso"
  "risk_level": "alto",
  "summary": "Posible conversación inapropiada detectada",
  "keywords": ["privado", "edad"],
  "notified_to": ["tutor@escuela.com"]
}

4. users (Administradores, Padres, Tutores)
{
  "_id": ObjectId,
  "email": "tutor@escuela.com",
  "name": "María Gómez",
  "role": "tutor",
  "devices_monitored": ["00:1A:2B:3C:4D:5E"],
  "receive_notifications": true
}
5. reports (Resúmenes Diarios o Semanales)
{
  "_id": ObjectId,
  "report_date": ISODate("2025-05-13"),
  "mac_address": "00:1A:2B:3C:4D:5E",
  "alerts_count": 3,
  "active_times": [
    { "from": "15:00", "to": "17:30" },
    { "from": "20:00", "to": "21:00" }
  ],
  "keywords_summary": ["edad", "privado", "chat"],
  "risk_levels": {
    "bajo": 2,
    "medio": 1,
    "alto": 0
  }
}

6. ssl_cert_logs (Intentos de evasión del MITM)
{
  "_id": ObjectId,
  "mac_address": "44:55:66:77:88:99",
  "timestamp": ISODate,
  "event": "SSL handshake fallido",
  "attempted_url": "https://red-social.com",
  "alert_issued": true
}

 Relaciones entre documentos (por referencia o embebidos)
traffic_logs referencia a devices por mac_address.


alerts pueden contener parte del traffic_log embebido.


users monitorean múltiples devices.


reports pueden consolidar eventos desde traffic_logs y alerts.







