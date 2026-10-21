# Mateline — Plan de negocio para Australia

> Versión adaptada del modelo de Antomatic (antomatic.pro) al mercado australiano.
> Fecha: 21 oct 2026. Etiquetas: **Confirmado** (fuente citada), **Probable** (inferido), **Incierto** (validar antes de decidir).

---

## 1. Qué hace Antomatic (análisis de la captura)

- **Propuesta:** "Más ventas, sin contestar lo mismo cien veces". Un chatbot entrenado con la info del negocio que atiende, recomienda, agenda y vende 24/7.
- **Canales:** Web y WhatsApp; Instagram "próximamente".
- **Fricción mínima:** "Conversaciones ilimitadas · Demo personalizado en horas · Sin tarjeta".
- **Navegación:** Industrias, Demo, Precio, Iniciar sesión → venden por vertical y con demo en vivo.
- **Modelo (Probable):** SaaS mensual para PYMEs hispanohablantes, con onboarding "hecho por ti".
- **No pude ver:** precios ni detalles internos — el sitio no cargó desde mi entorno. Todo lo anterior sale solo de la captura.

**Qué copiar:** demo gratis personalizada antes de pagar, mensajes centrados en el dolor (preguntas repetidas, ventas perdidas fuera de horario), precio plano sin límite de conversaciones.

**Qué cambiar para Australia:** canal (SMS > WhatsApp), nicho concreto en vez de "cualquier negocio", precios en AUD con GST, cumplimiento de la Spam Act.

---

## 2. Nicho recomendado: tradies (oficios a domicilio)

Fontaneros, electricistas, aire acondicionado, cerrajeros, techadores, jardineros, limpieza.

**Por qué:**
- **Probable:** están "en la obra" con las manos ocupadas → pierden llamadas y consultas web, y cada trabajo perdido vale cientos de dólares.
- **Confirmado:** ya existen productos dirigidos a ese dolor (p. ej. TransferToAI desde AUD $99/mes, Made 4 Tradies) → hay demanda probada.
- **Confirmado:** Australia tiene ~2,73 M de negocios activos (ABS, jun 2025); el desglose de construcción está en los data cubes de ABS (no lo verifiqué).

**Por qué no clínicas como primer nicho:**
- Datos de salud = información sensible → la Ley de Privacidad aplica aunque facturen < AUD $3 M (**Confirmado** por fuentes secundarias; validar con OAIC). Más riesgo legal para empezar.

**Riesgo honesto (Confirmado):** una guía (13Labs) dice que el mayor dolor de muchos tradies es el papeleo de presupuesto→factura, no conseguir leads. Valídalo en entrevistas antes de invertir.

---

## 3. Producto (MVP)

| Función | Detalle |
|---|---|
| Chat web 24/7 | Widget entrenado con servicios, zonas, precios orientativos, FAQs |
| Captura de lead | Nombre, suburbio, tipo de trabajo, fotos, urgencia |
| **Missed-call text-back** | Si el tradie no contesta, se envía un SMS automático y el bot sigue la conversación |
| Agenda | Propone horarios y los manda al calendario (Google/Outlook) |
| Resumen al tradie | SMS/email con el lead listo para cotizar |
| Integraciones (fase 2) | ServiceM8, Tradify, Xero — confirmar APIs con cada proveedor (**Incierto**) |
| Canales extra | Facebook/Instagram Messenger; WhatsApp como opcional |

**Sobre WhatsApp (Probable):** en Australia se usa bastante menos que en Latam (~33 % de penetración según fuentes secundarias). El SMS es el canal por defecto para negocios locales.

**Stack sugerido:** LLM (API de Claude) + base de conocimiento por cliente, Twilio o proveedor local de SMS con número australiano, Supabase para datos, widget JS embebible.

---

## 4. Precios (AUD, GST incluido)

| Plan | Precio | Incluye |
|---|---|---|
| **Starter** | $99/mes | Chat web, captura de leads, resumen por SMS/email |
| **Pro** | $199/mes | + missed-call text-back, agenda, Messenger, 500 SMS |
| **Crew** | $349/mes | + varios técnicos/ubicaciones, integraciones, informes |

- Setup "hecho por ti" gratis los primeros 3 meses de lanzamiento; luego $299.
- Demo personalizada gratis en 24 h, sin tarjeta (igual que Antomatic).
- **Referencia (Confirmado, fuentes de proveedores):** chat/IA para pequeñas empresas suele estar entre AUD $50–$300/mes; recepción humana virtual entre $250–$900/mes. Nuestro precio cabe en ese rango.
- **Incierto:** el coste real de SMS y LLM por cliente — calcúlalo con 5 clientes piloto antes de fijar precios.

---

## 5. Competencia

- **Directa (tradies AU):** TransferToAI, Made 4 Tradies, agencias GoHighLevel.
- **Indirecta:** Podium, recepcionistas virtuales humanos, chatbots genéricos (Intercom, Tidio, Chatbase).
- **Diferenciación:**
  1. Texto (chat + SMS), no voz → más barato y fiable.
  2. Demo con *su propia web* en 24 h.
  3. Configuración hecha por nosotros; el tradie no toca nada.
  4. Precio plano en AUD, sin contrato.

---

## 6. Legal y cumplimiento (validar con un abogado australiano)

- **Spam Act 2003 (Confirmado):** SMS comerciales requieren consentimiento, identificación del remitente y opción de baja. La ACMA multa fuerte (CBA pagó AUD $7,5 M en 2024). → Los SMS de respuesta a una consulta del cliente son transaccionales (**Probable**), pero no mandes marketing sin consentimiento.
- **Privacy Act 1988:** exención para empresas < AUD $3 M sigue vigente pero con excepciones y reforma en curso (**Incierto** — revisar OAIC). Recomendación: cumplir los APPs desde el día 1 (política de privacidad, datos alojados en Australia si es posible).
- **Empresa:** ABN, registro de nombre comercial en ASIC, GST si facturas ≥ AUD $75k/año.
- **Marca "Mateline":** **no verificada**. Revisar disponibilidad en IP Australia (trademarks), ASIC y dominio .com.au antes de usarla.
- **Si no vives en Australia (Incierto):** necesitarás una estructura válida (empresa australiana con director residente o vender desde tu país). Consulta a un contador.

---

## 7. Go-to-market (primeros 90 días)

1. **Semanas 1–2:** 15 entrevistas con tradies (grupos de Facebook, Hipages, conocidos). Pregunta: ¿cuántas llamadas pierdes por semana? ¿qué vale un trabajo medio?
2. **Semanas 3–6:** MVP + 5 pilotos gratis a cambio de testimonio y datos.
3. **Semanas 7–12:** outbound — busca en Google Maps tradies con web pero sin chat, crea su demo y mándales el enlace ("Te armé esto con tu web, pruébalo").
4. Canales: grupos de Facebook de tradies, asociaciones (Master Plumbers, Master Electricians), proveedores (Reece, Bunnings Trade), referidos (1 mes gratis por referido).

**Meta (supuesto, no previsión):** 30 clientes × $199 ≈ AUD $6k/mes de ingreso recurrente al mes 6.

---

## 8. Supuestos clave — confírmalos o corrígelos

1. Venderás en inglés a negocios australianos (no a la comunidad hispana en Australia).
2. Arrancas con un solo nicho (tradies) y te expandes después.
3. Producto de texto (chat + SMS), sin agente de voz al principio.
4. Puedes operar legalmente en Australia o vender desde fuera.
5. El nombre "Mateline" es provisional.

---

## Fuentes

- [TransferToAI – Product Hunt](https://www.producthunt.com/products/transfertoai-australia-ai-receptionist)
- [Crescendo Lab – AI receptionist pricing](https://blog.cresclab.com/en/ai-receptionist)
- [callin.io – Virtual reception Australia](https://callin.io/virtual-reception-australia-what-you-need-to-know-before-choosing/)
- [Made 4 Tradies – AI Directory (industry.gov.au)](https://aidirectory.industry.gov.au/organisation/made-4-tradies)
- [13Labs – AI automation for Australian trades](https://www.13labs.au/guides/ai-automation-australian-trades-what-actually-helps)
- [ABS – Counts of Australian Businesses](https://www.abs.gov.au/statistics/economy/business-indicators/counts-australian-businesses-including-entries-and-exits)
- [Rasayel – WhatsApp statistics](https://learn.rasayel.io/en/blog/whatsapp-user-statistics/)
- [Sinch – SMS marketing laws Australia](https://sinch.com/engage/resources/sms-compliance/sms-marketing-laws-australia/)
- [Sprintlaw – Spam Act compliance](https://sprintlaw.com.au/articles/spam-act-compliance-australian-legal-guide-for-businesses/)
- [Pinsent Masons – ACMA enforcement](https://www.pinsentmasons.com/out-law/analysis/acma-australian-scams-report)
- [Clym – Australian data privacy regulation](https://www.clym.io/blog/australian-data-privacy-regulation-what-you-need-to-know)
- [QLS – AML/CTF Starter Guide](https://www.qls.com.au/getmedia/58d2d0fb-424a-442d-8f0b-9672b8b0e84f/AML-CTF_Starter-Guide.pdf?ext=.pdf)
