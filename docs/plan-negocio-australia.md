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

## 5. Análisis de mercado y competencia

### Respuesta corta: sí, ya existen muchas empresas que hacen esto en Australia

El mercado está **activo y bastante saturado**. No es una idea nueva allí; hay que entrar con una diferencia clara.

### Tamaño y adopción

- **Mercado de IA conversacional en Australia:** ~USD 500 M en 2025, previsión ~USD 6.000 M en 2034 (IMARC; una sola consultora → estimación, no dato firme).
- **Adopción de IA en pequeñas empresas (Confirmado, ABS 2024–25):** ~11 % de las pequeñas/micro empresas usaba IA. → Mucho espacio por crecer.
- **Encuestas privadas** dan cifras mucho más altas (43 %–72 %) porque cuentan cualquier uso, incluso ChatGPT ocasional. Tómalas con cautela.
- **Atención al cliente** es uno de los usos más citados (~32 % según una encuesta secundaria).

### Competidores encontrados (precios según sus webs o comparativas; no verificados por mí)

**A. Recepcionistas IA por voz para tradies — el segmento más saturado**

| Empresa | Origen | Precio publicado | Notas |
|---|---|---|---|
| Sophiie | Australia | ~$89–$300/mes + setup ~$400–$800 | Muy enfocada en tradies; precios contradictorios entre fuentes |
| Jodie (heyjodie) | — | Desde A$99/mes plano | Captura el trabajo y lo manda por SMS; sin setup |
| Relay (Leva) | Australia | $199/mes | Integración con ServiceM8 |
| TransferToAI | Australia | Desde A$99/mes | Agenda en ServiceM8 + resumen SMS |
| Miyai | — | Chat desde A$19/mes; voz desde A$199/mes | Precio muy bajo en chat |
| Valory | Australia | A$149–1.299/mes + setup desde A$990 | Más enterprise |
| Rosie | EE. UU. | USD $49–$299/mes | Sin acento australiano |
| Made 4 Tradies | Australia | Sin precio público | Chat, presupuestos IA, voz; Xero/ServiceM8/Tradify |

**B. Chatbots web / multicanal para PYMEs (agencias locales)**

| Empresa | Precio / oferta |
|---|---|
| chatbot.net.au | Desde $99/mes, listo en 5–7 días, demo gratis |
| Systree | SMS, Facebook, Instagram, WhatsApp, web; registra en CRM |
| Stacked Digital | Chat web + SMS bidireccional + agenda |
| RightLink | Presupuesto fijo, ~2 semanas hasta salir en vivo |
| Dynamic Marketing Australia | Chatbot de captura de leads |

**C. Herramientas globales autoservicio:** Tidio (plan gratis), Intercom, Chatbase, Podium, GoHighLevel (lo usan muchas agencias).

### Qué significa esto (mi interpretación)

- **Probable:** la demanda existe — tantos competidores indican que los clientes pagan.
- **Probable:** el precio de entrada ya está fijado en **~A$99/mes**, y Miyai ofrece chat desde A$19. Mi plan Starter de $99 **no destaca** solo por precio.
- **Probable:** la mayoría compite en **voz**. El chat + SMS es menos ruidoso pero también tiene oferta (chatbot.net.au, Stacked Digital).
- **Riesgo:** entrar como "otro chatbot genérico" desde fuera de Australia, sin marca ni red local, es difícil.

### Cómo diferenciarse (opciones, de más a menos recomendada)

1. **Hiper-nicho vertical:** un solo oficio (p. ej. aire acondicionado, control de plagas o limpieza) con flujos, preguntas y presupuestos específicos. Los competidores son "para todos los tradies".
2. **Presupuesto con fotos:** el cliente sube fotos y el bot genera un presupuesto orientativo para que el tradie lo apruebe. Ataca el dolor de papeleo que señala 13Labs.
3. **Comunidad latina en Australia:** negocios de limpieza, construcción y servicios gestionados por hispanohablantes, con soporte en español y bot en inglés. Ventaja: hablas su idioma y la competencia no. (**Incierto:** no verifiqué el tamaño de ese segmento.)
4. **Agencia "hecho por ti" + alianzas:** venderte a través de contables, diseñadores web o proveedores de software (ServiceM8, Tradify) en vez de competir en anuncios.

**Diferenciadores base (mantener):** demo con *su propia web* en 24 h, configuración hecha por nosotros, precio plano en AUD, sin contrato.

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
- [IMARC – Australia Conversational AI Market](https://www.imarcgroup.com/australia-conversational-ai-market)
- [LeadsNow – ABS AI adoption by business size](https://leadsnow.ai/ai-adoption-australian-businesses/)
- [QuickBooks – AI Impact Report Australia 2026](https://quickbooks.intuit.com/au/blog/news/ai-impact-report-australia-2026/)
- [ServiceScale – Sophiie review](https://www.servicescale.com.au/apps-for-tradies/crm-marketing/sophiie-ai)
- [Valory – Best AI receptionist Australia](https://www.valory.com.au/resources/best-ai-receptionist-australia)
- [Jodie – Best AI receptionist Australia](https://heyjodie.com/en-au/guides/best-ai-receptionist/)
- [Relay – Compare](https://levasolutions.com.au/relay/compare)
- [Miyai – Guide](https://miyai.ai/guides/best-ai-receptionist-2026)
- [TransferToAI – 11 best AI answering services](https://transfertoai.com/blog/best-ai-answering-services-australia)
- [chatbot.net.au](https://chatbot.net.au/)
- [Systree](https://systree.com.au/conversational-ai)
- [Stacked Digital](https://stackeddigital.com/services/ai-chatbots/)
- [RightLink](https://rightlink.io/ai-chatbot)
- [Aussie Business AI – Chatbot comparison](https://aussiebusinessai.com.au/blog/ai-chatbot-small-business-australia)
