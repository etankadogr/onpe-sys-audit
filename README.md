# 🗳️ El voto no termina en la urna. Termina en el código que lo cuenta.

> *Durante las elecciones más disputadas de los últimos años, el sistema que publicaba
> los resultados en tiempo real tenía el padrón de 27 millones de peruanos abierto al mundo —
> sin contraseña, sin límite de consultas, sin registro de quién accedió.*

Nadie lo hackeó. Pero tampoco nadie puede probar que nadie lo intentó.

Eso se llama **desconfianza legítima**. Y la desconfianza legítima, en una democracia
polarizada, es casi tan destructiva como el fraude mismo.

---

## ¿Qué encontramos?

| # | Vulnerabilidad | Severidad | Impacto |
|---|---|---|---|
| H3 | Padrón electoral sin autenticación ni rate limiting | 🔴 **Alta** | 27M de DNIs consultables sin restricción |
| H4 | Swagger UI + arquitectura interna expuesta en producción | 🔴 **Alta** | Mapa completo del sistema para cualquier actor |
| H2 | Sin límite de velocidad en ningún endpoint | 🟠 **Media** | Enumeración masiva posible, sin trazas |
| H1 | Control de acceso basado en headers falsificables | 🟠 **Media** | Cualquier script automatizado tiene acceso total |
| H5 | Paginación sin límite máximo | 🟠 **Media** | DoS potencial · 2.5 MB por request |
| H7 | CSP débil con nonce sin inyectar | 🟡 **Baja** | `unsafe-inline` como único mecanismo activo |

> **Metodología:** análisis pasivo exclusivamente — inspector del navegador, tráfico HTTP,
> headers de respuesta. Sin ataques, sin enumeración masiva, sin cruzar ninguna línea legal.
> Todo bajo Ley N° 27806 y D.L. 1412.

---

## El problema no es técnico. Es institucional.

No estamos divididos por los resultados.  
Estamos divididos porque no tenemos la **certeza técnica** de que el proceso fue limpio.

Esa certeza no se construye con declaraciones.  
Se construye con auditorías independientes, sistemas verificables,  
e instituciones que entiendan que la transparencia no es una opción política:

**es una obligación de ingeniería.**

---

## ¿Qué exigir?

- [ ] Deshabilitar Swagger y OpenAPI en producción antes de cada proceso electoral
- [ ] Rate limiting real en todos los endpoints públicos — especialmente `/padron/mesa/{dni}`
- [ ] Autenticación del propio elector para consultar su mesa de votación
- [ ] Auditoría de logs del endpoint del padrón para el proceso 2026
- [ ] Proceso de revisión de seguridad independiente obligatorio antes de cada despliegue electoral

---

## El Perú merece elecciones que no solo sean limpias —

## sino que puedan ser **demostradas** como limpias.

> Ante cualquier ciudadano. Con cualquier herramienta. En cualquier momento.

---

<sub>
Análisis técnico independiente · 19 de abril de 2026 · Lima, Perú<br>
<strong>Srinivasa Ramanujan</strong> — WIC / Wasi Innovation Consulting<br>
Investigación defensiva sobre datos públicos · Ley N° 27806 · D.L. 1412 · Licencia ODC-BY
</sub>
