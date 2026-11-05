# Senior Marketing Suite (PY)

Plugin multiplataforma que incorpora la skill **Senior Marketing Professional** para convertir objetivos de negocio en estrategias, campañas y decisiones de marketing profesionales, respaldadas por evidencia y adaptadas al mercado paraguayo.

Funciona como paquete de plugin en Google Antigravity y Claude Code. La skill utiliza el estándar abierto `SKILL.md`, por lo que también puede reutilizarse en otros agentes compatibles con Agent Skills.

## Identidad

- **Nombre del plugin:** `senior-marketing-suite`
- **Nombre visible:** Senior Marketing Suite (PY)
- **Skill incluida:** `senior-marketing-professional`
- **Versión:** `1.1.0`

## Qué hace

La skill ayuda a:

- convertir objetivos generales en resultados observables y medibles;
- responder en el idioma del usuario, salvo que se solicite otro;
- identificar audiencias, problemas, objeciones y comportamientos esperados;
- definir posicionamiento, propuesta de valor y mensajes;
- diseñar estrategias, campañas, lanzamientos y planes de canal;
- auditar embudos y detectar el principal cuello de botella;
- priorizar iniciativas por impacto, evidencia, esfuerzo, tiempo y riesgo;
- preparar reportes ejecutivos y planes de acción;
- definir KPI, escenarios, experimentos y criterios para continuar, corregir o detener una iniciativa;
- localizar la estrategia por ciudad, departamento, zona fronteriza o cobertura nacional en Paraguay;
- trabajar con idioma, moneda, zona horaria, estacionalidad, distribución y evidencia local;
- incorporar controles para publicidad, comercio electrónico, marketing directo, datos personales y propiedad intelectual en Paraguay.

La skill diferencia hechos, interpretaciones, supuestos y recomendaciones. No inventa datos, benchmarks, atribución, testimonios ni resultados.

## Integraciones de datos

La skill puede trabajar con un plugin, conector o servidor MCP de marketing disponible en el agente que la ejecuta. Incluye instrucciones específicas para utilizar [**Supermetrics Marketing Analytics**](https://claude.com/marketplace/connectors/supermetrics) —o una integración equivalente— cuando la tarea requiere datos actuales de campañas, presupuestos, atribución, embudos o dashboards.

Supermetrics no está incluido ni se instala desde este repositorio. Cada usuario debe conectarlo por separado en la plataforma donde esté disponible. Si no existe una integración conectada, la skill puede trabajar con datos proporcionados por el usuario o con archivos exportados.

Para datos de Paraguay, la skill comprueba la moneda, la zona horaria, el modelo de atribución y el origen de cada métrica. No suma ingresos atribuidos por distintas plataformas sin reconciliar duplicaciones y ventanas de atribución.

## Estructura

```text
senior-marketing-professional-skill/
├── .antigravity-plugin/
│   └── plugin.json
├── .claude-plugin/
│   └── plugin.json
├── skills/
│   └── senior-marketing-professional/
│       ├── SKILL.md
│       ├── agents/
│       │   └── openai.yaml
│       └── references/
│           ├── measurement.md
│           └── paraguay-marketing-compliance.md
└── README.md
```

Los manifiestos identifican el mismo paquete como **Senior Marketing Suite (PY)** en cada plataforma. El contenido profesional permanece en `skills/senior-marketing-professional/` y no depende de una marca o modelo específico. `agents/openai.yaml` agrega metadatos visuales opcionales para Codex y ChatGPT; otras plataformas pueden ignorarlo.

### Qué es cada archivo

- `SKILL.md`: contiene el criterio profesional, el flujo de trabajo y las reglas principales de la skill.
- `agents/openai.yaml`: define el nombre, la descripción breve y el prompt sugerido que muestran Codex y ChatGPT.
- `references/measurement.md`: contiene fórmulas, criterios de atribución, pronósticos y diseño de experimentos; se consulta solo cuando la tarea lo requiere.
- `references/paraguay-marketing-compliance.md`: contiene el checklist operativo y las fuentes oficiales paraguayas para publicidad, ecommerce, contacto móvil, datos personales, propiedad intelectual y competencia.
- `.antigravity-plugin/plugin.json`: manifiesto de instalación y descubrimiento para Google Antigravity.
- `.claude-plugin/plugin.json`: manifiesto de instalación y descubrimiento para Claude Code.

## Instalación en Google Antigravity

Clona el repositorio y valida el plugin:

```bash
git clone https://github.com/Taoista/senior-marketing-professional-skill.git
agy plugin validate --strict ./senior-marketing-professional-skill
agy plugin install ./senior-marketing-professional-skill
```

Después puedes invocar la skill con:

```text
/senior-marketing-professional
```

También puede activarse automáticamente cuando la solicitud coincide con su descripción.

## Instalación en Claude Code

Durante desarrollo, clona el repositorio y carga el plugin desde su carpeta:

```bash
git clone https://github.com/Taoista/senior-marketing-professional-skill.git
claude --plugin-dir ./senior-marketing-professional-skill
```

La skill queda disponible dentro del namespace del plugin:

```text
/senior-marketing-suite:senior-marketing-professional
```

Claude también puede activarla automáticamente cuando el contexto de la solicitud resulta pertinente.

## Uso como skill independiente

Si el agente admite Agent Skills pero no plugins, copia esta carpeta a su directorio de skills:

```text
skills/senior-marketing-professional/
```

El archivo obligatorio es `SKILL.md`; las referencias `measurement.md` y `paraguay-marketing-compliance.md` deben conservarse en la misma estructura relativa.

## Ejemplos

### Estrategia

```text
Crea una estrategia de marketing para una empresa B2B SaaS de Paraguay que
quiere aumentar su pipeline calificado durante los próximos seis meses. Separa
hechos, supuestos y recomendaciones y justifica cualquier benchmark extranjero.
```

### Auditoría con datos conectados

```text
Usa la integración de marketing disponible para revisar el último trimestre.
Identifica el principal cuello de botella, separa métricas reportadas por cada
plataforma y prioriza tres intervenciones.
```

### Reporte ejecutivo

```text
Convierte estos datos en un reporte ejecutivo. Explica qué cambió, por qué
podría haber cambiado, el impacto comercial, el nivel de confianza y las
decisiones que debe tomar la dirección.
```

### Campaña y cumplimiento en Paraguay

```text
Diseña una campaña de adquisición para Paraguay. Incluye audiencia, propuesta,
canales, presupuesto en PYG, medición y un checklist de publicidad, datos
personales, contacto móvil y derechos sobre los contenidos.
```

## Enfoque legal paraguayo

La skill utiliza como puntos de control, entre otras fuentes oficiales:

- Ley N.º 1334/1998 de Defensa del Consumidor y del Usuario;
- Ley N.º 6366 sobre transparencia y Costo Total de Crédito en ofertas financiadas;
- Ley N.º 4868/2013 de Comercio Electrónico;
- Ley N.º 5830/2017 sobre publicidad no autorizada por telefonía móvil;
- Ley N.º 6534/2020 de Protección de Datos Personales Crediticios;
- Ley N.º 7593/2025 de Protección de Datos Personales, cuya entrada en vigor está prevista para finales de 2027;
- Ley N.º 1294/1998 de Marcas y Ley N.º 1328/1998 de Derecho de Autor y Derechos Conexos;
- Ley N.º 4956/2013 de Defensa de la Competencia cuando corresponda.

Estas referencias funcionan como alertas operativas, no como asesoría jurídica. Para campañas materiales, categorías reguladas o decisiones de alto riesgo debe intervenir un profesional jurídico habilitado en Paraguay. El archivo `paraguay-marketing-compliance.md` indica la fecha de revisión y enlaza las fuentes oficiales.

## Seguridad y autorizaciones

La skill puede analizar información y preparar borradores, pero no autoriza automáticamente a publicar contenidos, enviar comunicaciones, cambiar presupuestos, modificar segmentaciones, editar campañas o registros de CRM ni contactar clientes.

Antes de una acción externa debe confirmarse la cuenta, audiencia, contenido, presupuesto, fecha y autoridad de aprobación. Las credenciales se configuran mediante los flujos seguros de cada plataforma y nunca deben pegarse en una conversación.

## Sidecars y hooks

Un **sidecar** es un proceso persistente administrado por Antigravity para trabajos programados o reacciones a eventos. No es una tarjeta visual y no forma parte del estándar portable de Agent Skills.

Este plugin no incluye sidecars ni hooks todavía. Agregarlos sin una automatización concreta produciría procesos innecesarios y comportamientos distintos entre plataformas. Se pueden incorporar posteriormente cuando estén definidos el evento, la acción, la frecuencia, la fuente de datos y las condiciones de aprobación.
