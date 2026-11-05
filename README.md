# Senior Marketing Suite

Plugin multiplataforma que incorpora la skill **Senior Marketing Professional** para convertir objetivos de negocio en estrategias, campañas y decisiones de marketing respaldadas por evidencia.

Funciona como paquete de plugin en Google Antigravity y Claude Code. La skill utiliza el estándar abierto `SKILL.md`, por lo que también puede reutilizarse en otros agentes compatibles con Agent Skills.

## Identidad

- **Nombre del plugin:** `senior-marketing-suite`
- **Nombre visible:** Senior Marketing Suite
- **Skill incluida:** `senior-marketing-professional`
- **Versión:** `1.0.0`

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
- definir KPI, escenarios, experimentos y criterios para continuar, corregir o detener una iniciativa.

La skill diferencia hechos, interpretaciones, supuestos y recomendaciones. No inventa datos, benchmarks, atribución, testimonios ni resultados.

## Integraciones de datos

La skill puede trabajar con un plugin, conector o servidor MCP de marketing disponible en el agente que la ejecuta. Incluye instrucciones específicas para utilizar **Supermetrics Marketing Agent** —o una integración equivalente— cuando la tarea requiere datos actuales de campañas, presupuestos, atribución, embudos o dashboards.

Supermetrics no está incluido ni se instala desde este repositorio. Cada usuario debe conectarlo por separado en la plataforma donde esté disponible. Si no existe una integración conectada, la skill puede trabajar con datos proporcionados por el usuario o con archivos exportados.

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
│           └── measurement.md
└── README.md
```

Los manifiestos identifican el mismo paquete como **Senior Marketing Suite** en cada plataforma. El contenido profesional permanece en `skills/senior-marketing-professional/` y no depende de una marca o modelo específico. `agents/openai.yaml` agrega metadatos visuales opcionales para Codex y ChatGPT; otras plataformas pueden ignorarlo.

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

El archivo obligatorio es `SKILL.md`; la referencia `measurement.md` debe conservarse en la misma estructura relativa.

## Ejemplos

### Estrategia

```text
Crea una estrategia de marketing para una empresa B2B SaaS que quiere aumentar
su pipeline calificado durante los próximos seis meses. Separa hechos, supuestos
y recomendaciones.
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

## Seguridad y autorizaciones

La skill puede analizar información y preparar borradores, pero no autoriza automáticamente a publicar contenidos, enviar comunicaciones, cambiar presupuestos, modificar segmentaciones, editar campañas o registros de CRM ni contactar clientes.

Antes de una acción externa debe confirmarse la cuenta, audiencia, contenido, presupuesto, fecha y autoridad de aprobación. Las credenciales se configuran mediante los flujos seguros de cada plataforma y nunca deben pegarse en una conversación.

## Sidecars y hooks

Un **sidecar** es un proceso persistente administrado por Antigravity para trabajos programados o reacciones a eventos. No es una tarjeta visual y no forma parte del estándar portable de Agent Skills.

Este plugin no incluye sidecars ni hooks todavía. Agregarlos sin una automatización concreta produciría procesos innecesarios y comportamientos distintos entre plataformas. Se pueden incorporar posteriormente cuando estén definidos el evento, la acción, la frecuencia, la fuente de datos y las condiciones de aprobación.
