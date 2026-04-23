---
layout: page
title: Política de Privacidad
permalink: /es/privacidad/
lang: es
---

> 🌐 **Idioma:** [PT](/privacidade/) · [EN](/en/privacy/) · **ES**

> Esta es una traducción de cortesía del documento original en portugués. En caso de cualquier discrepancia, prevalece la [versión en portugués](https://geninho.app.br/privacidade/).

# Política de Privacidad — Geninho

**Última actualización:** 21 de abril de 2026

## 1. Quiénes somos y finalidad de esta Política
El **Geninho** es una aplicación iOS de apoyo educativo para familias brasileñas, enfocada en la organización escolar, el plan de estudios con IA y la validación de finalización mediante cuestionario.

Esta Política describe, en lenguaje claro, **qué datos tratamos, por qué los tratamos, con quién los compartimos y qué derechos tienes** como titular, en cumplimiento de la **Ley General de Protección de Datos Personales de Brasil (LGPD, Ley Federal n.º 13.709/2018)** y de las exigencias de la App Store.

**Responsable del tratamiento:**
- Responsable: **Pablo Rodrigo (desarrollador independiente)**
- Jurisdicción: Recife/PE — Brasil
- Canal de contacto para privacidad, LGPD y seguridad: **suporte@geninho.app.br**

Datos de identificación adicionales (documento y dirección completa) pueden ser proporcionados mediante solicitud formal y fundamentada, conforme a la LGPD, a través del canal de contacto anterior.

> **Nota para personas fuera de Brasil:** Esta app se desarrolla y opera desde Brasil. Los usuarios fuera de Brasil son bienvenidos; atendemos solicitudes de titulares de datos conforme a las leyes de privacidad aplicables de buena fe, pero el marco legal rector del tratamiento de datos es la ley brasileña.

## 2. Principios que adoptamos
- **Minimización:** recopilamos solo lo necesario para el funcionamiento del servicio.
- **Finalidad específica:** cada dato se utiliza para un propósito informado.
- **Transparencia:** esta Política enumera los proveedores y los tipos de datos.
- **Seguridad por defecto:** los datos en tránsito y en reposo utilizan las protecciones de los proveedores listados en la sección 6.
- **Control parental:** los perfiles de niños y niñas se crean y gestionan únicamente por una persona responsable con cuenta vinculada a la misma familia.

## 3. Datos que tratamos

### 3.1 Datos de autenticación (responsable)
- correo electrónico;
- nombre de visualización (cuando lo proporciona el proveedor);
- identificadores técnicos de las cuentas (Firebase Auth UID, Apple Sign-In identifier, Google account ID cuando corresponda);
- correo electrónico anónimo de relay de Apple, cuando el usuario elige "Ocultar mi correo".

**La biometría (Face ID / Touch ID)** es procesada exclusivamente en el dispositivo por iOS. Geninho **no recibe ni transmite datos biométricos** — solo el resultado booleano "autenticado / no autenticado".

### 3.2 Datos de la familia y de los niños
- nombre de la familia;
- rol de los usuarios (`ownerParent`, `parent`, `child`);
- vínculos entre responsables y niños;
- por cada niño: nombre, año/grado escolar, configuraciones de estudio (franja horaria, duración, porcentaje mínimo de acierto en el cuestionario, permiso de YouTube), monedas, racha y logros.

Los niños **no crean cuentas por sí mismos**. El perfil lo crea el responsable, que es titular del vínculo y responde por los datos del menor (ver sección 9).

### 3.3 Datos escolares y pedagógicos
- escuela(s) registrada(s) y periodos;
- horario de clases por niño (materia, día, horario);
- plan del año escolar (materias, temas);
- exámenes/actividades (materia, fecha, temas, nota cuando se informa);
- sesiones de estudio generadas, completadas o no;
- resultados de cuestionarios (porcentaje de acierto, intentos, comentarios sobre preguntas);
- perfil adaptativo por niño (mejores franjas de estudio, dominio por materia/tema).

### 3.4 Datos generados por IA
- texto extraído por OCR de imágenes/PDFs que importas (horario, calendario de exámenes);
- preguntas enviadas por el niño al **chat libre de Geninho** (Premium);
- respuestas generadas por IA;
- **clasificación automatizada** de la pregunta (normal, solicitud directa de respuesta, contenido inapropiado, sospecha) y motivo, cuando corresponda;
- las preguntas clasificadas como `direct_homework`, `inappropriate` o `suspicious` quedan accesibles al responsable de la familia para revisión (colección `flaggedQuestions`).

### 3.5 Datos de uso y suscripción
- contadores mensuales de uso (planes de IA generados, preguntas al chat) para aplicar los límites del plan;
- contadores totales (importaciones por OCR);
- identificador de la transacción de StoreKit y producto de la suscripción (`com.geninho.app.premium.monthly` / `.yearly`) — **no recibimos datos de tarjetas**; el cobro es 100% de Apple.

### 3.6 Datos técnicos y de publicidad (solo plan gratuito)
- En la versión gratuita, mostramos anuncios de **Google AdMob**. Antes de solicitar anuncios personalizados, pedimos tu consentimiento mediante el aviso nativo de Apple (**App Tracking Transparency — ATT**).
- Si **autorizas** el rastreo, AdMob puede usar el IDFA (identificador de publicidad de Apple) para mostrar anuncios más relevantes.
- Si **no autorizas**, AdMob muestra solo anuncios no personalizados y el IDFA no se comparte.
- Geninho **no** recopila el IDFA para ningún propósito más allá de la exhibición de anuncios en AdMob.

### 3.7 Notificaciones
La app utiliza **únicamente notificaciones locales** (recordatorios de estudio, exámenes próximos, logros). No usamos servicio de push ni enviamos tokens de dispositivo a servidores externos.

## 4. Finalidades y bases legales (LGPD art. 7)

| Finalidad | Datos utilizados | Base legal |
|---|---|---|
| Crear y autenticar cuenta | correo, identificadores de proveedor | Ejecución de contrato |
| Organizar rutina escolar | datos de 3.2, 3.3 | Ejecución de contrato |
| Generar plan de estudios y cuestionarios con IA | 3.3 y 3.4 | Ejecución de contrato |
| Validar sesión de estudio por cuestionario | 3.3, 3.4 | Ejecución de contrato |
| Aplicar límites del plan Free y cobrar Premium | 3.5 | Ejecución de contrato |
| Moderación de chat y seguridad del menor | 3.4 | Interés legítimo + protección del mejor interés del niño |
| Mostrar anuncios en el plan gratuito | 3.6 | Consentimiento (ATT) |
| Prevenir fraude y garantizar seguridad | registros operativos | Interés legítimo |
| Cumplir obligaciones legales | cuando se exija | Cumplimiento de obligación legal |

## 5. Procesamiento de imágenes e IA

### 5.1 OCR
La extracción de texto de las imágenes/PDFs importados se realiza **en el propio dispositivo**, usando el framework Vision de Apple. Las imágenes **no** se envían a nuestros servidores ni a proveedores de IA.

### 5.2 Envío de texto a la IA
Después del OCR, **solo el texto extraído** (no la imagen) puede enviarse a los proveedores de IA (ver sección 6) para estructurarlo en clases, exámenes y temas. Recomendamos revisar los resultados antes de confirmar — la IA puede cometer errores.

### 5.3 Chat con Geninho
Las preguntas hechas al chat libre (Premium) y las respuestas generadas pasan por el proveedor de IA contratado. No utilizamos esas conversaciones para entrenar modelos de IA; los proveedores listados en la sección 6 tienen cláusulas contractuales de no-entrenamiento para datos de API.

### 5.4 Consentimiento obligatorio antes del envío a proveedores de IA
Antes del primer uso de cualquier función que dependa de IA en la nube (generación de plan, OCR estructurado, cuestionario, chat), la app muestra la pantalla **"Uso de Inteligencia Artificial"** que enumera:
- **Qué datos se enviarán** — textos extraídos de fotos/PDFs, materias y temas registrados, preguntas del chat y contexto pedagógico.
- **A quién** — OpenAI, Inc. (EE. UU.), Google LLC (EE. UU.) y, cuando esté configurado, Microsoft Corporation (Azure OpenAI).
- **Qué garantizamos** — los proveedores están contractualmente impedidos de entrenar modelos con tus datos; no enviamos datos financieros, contraseñas, ubicación ni identificadores personales más allá de lo necesario.

El usuario debe tocar **"Aceptar y continuar"** para habilitar las funciones de IA. Si elige **"Continuar sin IA"**, la app sigue funcionando con recursos locales (horario, exámenes, recordatorios, logros) y las llamadas a la nube quedan bloqueadas. La preferencia puede revisarse en cualquier momento en **Más → Preferencias de IA**. Mientras no haya aceptación, **no se envía ningún dato personal a los proveedores de IA**.

## 6. Operadores y proveedores (con quién compartimos datos)

Compartimos datos **solo con los proveedores estrictamente necesarios** para la operación del servicio:

| Proveedor | Función | Datos tratados | Lugar de procesamiento |
|---|---|---|---|
| **Google / Firebase** (Authentication, Firestore, Storage) | Autenticación y base de datos | Todos los datos de las secciones 3.1 a 3.5 | EE. UU. / multirregión |
| **Apple** (Sign in with Apple, StoreKit) | Inicio de sesión y cobro de suscripción | Identificador Apple, transacción de suscripción | EE. UU. |
| **Google** (Google Sign-In) | Inicio de sesión opcional con cuenta Google | correo, identificador Google | EE. UU. |
| **OpenAI** | Generación de cuestionarios, plan de estudios, OCR estructurado, chat | Texto (sin imágenes) de 3.3 y 3.4 | EE. UU. |
| **Google Gemini** | Respaldo de IA | Ídem | EE. UU. |
| **Azure OpenAI** (cuando está configurado) | Proveedor alternativo de IA | Ídem | EE. UU. / UE |
| **Google AdMob** | Anuncios en el plan gratuito | 3.6 | EE. UU. |

Los proveedores anteriores actúan como **operadores** (art. 5º, VII de la LGPD) bajo instrucción de Geninho. No vendemos datos personales y no los compartimos con fines de marketing de terceros.

### Transferencia internacional
Los datos pueden ser tratados en servidores ubicados fuera de Brasil (principalmente EE. UU.). Los proveedores listados adoptan cláusulas contractuales y salvaguardas compatibles con el art. 33 de la LGPD.

## 7. Retención y eliminación
- Los datos de la familia, de los niños y de estudios se conservan **mientras la cuenta esté activa**.
- Los registros de uso y límites del plan se conservan durante el ciclo necesario para operar los planes Free y Premium.
- **Eliminación de la cuenta:** disponible en la propia app ("Más" → eliminar cuenta) o por correo a `suporte@geninho.app.br`. Tras la solicitud, los datos personales identificables se eliminan de los sistemas activos en un plazo de **30 días**, observando las obligaciones legales y las limitaciones técnicas de las copias de seguridad.
- Los registros de transacciones de suscripción pueden conservarse durante el plazo legal aplicable (fiscal/consumerista) incluso después de la eliminación de la cuenta.

## 8. Seguridad
- Conexiones por HTTPS/TLS para todos los proveedores.
- Credenciales de API **nunca** embebidas en repositorios públicos (almacenadas en `Config.xcconfig` local).
- Separación de permisos por rol (responsable vs. niño).
- Autenticación mediante proveedores reconocidos (Apple, Google, Firebase Auth).
- Biometría opcional para desbloquear la app en el dispositivo.
- Revisión periódica de dependencias y buenas prácticas.

A pesar de los controles, ningún sistema es 100% inmune. Al identificar un incidente relevante que pueda generar riesgo a los titulares, seguiremos los procedimientos previstos en la LGPD (art. 48) y comunicaremos a la ANPD y a los titulares afectados cuando corresponda.

## 9. Datos de niños, niñas y adolescentes (LGPD art. 14)
- Geninho está destinado a **familias**, con perfiles de niños creados y operados **por el responsable**.
- La base legal para tratar datos de menores es el **mejor interés del niño**, mediante consentimiento específico y destacado del responsable en el momento del registro del perfil.
- El responsable tiene acceso a: datos de registro del niño, progreso escolar, preguntas realizadas al chat y elementos clasificados para revisión.
- No exigimos más datos del niño de los necesarios para la rutina escolar y el apoyo pedagógico.
- El chat libre cuenta con **clasificación automatizada** que bloquea contenido inapropiado y señala solicitudes de respuestas directas.
- El responsable puede, en cualquier momento, eliminar el perfil del niño en la app.

## 10. Tus derechos (LGPD art. 18)
Puedes ejercer, en cualquier momento, los siguientes derechos:

1. confirmación de la existencia de tratamiento;
2. acceso a los datos;
3. corrección de datos incompletos, inexactos o desactualizados;
4. anonimización, bloqueo o eliminación de datos innecesarios o excesivos;
5. portabilidad de los datos;
6. eliminación de los datos tratados con base en el consentimiento;
7. información sobre con quién compartimos los datos;
8. información sobre la posibilidad de no otorgar consentimiento y sus consecuencias;
9. revocación del consentimiento.

**Canal para ejercer derechos:** `suporte@geninho.app.br`. Responderemos en un plazo máximo de **15 días** corridos, conforme al art. 19 de la LGPD.

Si no obtienes una respuesta satisfactoria, puedes recurrir a la **Autoridad Nacional de Protección de Datos (ANPD)** en [https://www.gov.br/anpd](https://www.gov.br/anpd).

## 11. Contenido generado por IA — limitaciones
- Los planes de estudio, cuestionarios y respuestas del chat son apoyos pedagógicos y **pueden contener errores o imprecisiones**.
- El contenido no sustituye al docente, a la escuela ni al material didáctico oficial.
- Usa la IA como punto de partida; revisa siempre con sentido crítico.

## 12. Publicidad y rastreo
- El plan Free muestra anuncios a través de Google AdMob.
- Pedimos tu consentimiento para el rastreo mediante el aviso nativo de iOS (App Tracking Transparency).
- Tu respuesta a la ATT puede modificarse en cualquier momento en **Ajustes → Privacidad y Seguridad → Rastreo**.
- El plan Premium está **totalmente libre de anuncios**.

## 13. Actualizaciones de esta Política
Podemos revisar esta Política para reflejar cambios legales, técnicos o de producto. La versión vigente queda disponible dentro de la app (pantalla **Documentos Legales**) y en este repositorio. Los cambios sustanciales se comunicarán por el canal apropiado (aviso en la app o correo electrónico).

## 14. Contacto
- Correo de privacidad / LGPD: **suporte@geninho.app.br**
- Encargado del tratamiento de datos: el canal de contacto anterior atiende las solicitudes previstas en la LGPD. Por tratarse de una operación de pequeño porte conducida por un desarrollador independiente, se aplica el tratamiento flexibilizado previsto en la Resolución CD/ANPD n.º 2/2022 para agentes de tratamiento de pequeño porte.

---

**Resumen visual rápido (no sustituye al texto completo):**
- No vendemos datos.
- Usamos Firebase, OpenAI/Gemini/Azure, AdMob y Apple/Google para funcionar.
- El OCR se ejecuta en tu iPhone; solo el texto extraído se envía a la IA.
- Los niños no crean cuentas por sí mismos — siempre a través de un responsable.
- Puedes eliminar tu cuenta y solicitar copia de los datos en cualquier momento.
