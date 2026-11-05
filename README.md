# Profesional Senior de Marketing para Codex

Skill de marketing para Codex orientada a convertir objetivos de negocio en decisiones y planes accionables. Trabaja con criterio profesional senior en estrategia, posicionamiento, go-to-market, campañas, contenidos, lifecycle, CRM, medición y experimentación.

## Qué hace

La skill ayuda a:

- Traducir objetivos generales en resultados observables y medibles.
- Identificar audiencias, problemas, objeciones y comportamientos esperados.
- Definir posicionamiento, propuesta de valor y mensajes.
- Diseñar estrategias, campañas, lanzamientos y planes de canal.
- Auditar embudos y detectar el principal cuello de botella.
- Priorizar iniciativas por impacto, evidencia, esfuerzo, tiempo y riesgo.
- Preparar reportes ejecutivos y planes de acción.
- Definir KPI, escenarios, experimentos y criterios para decidir si continuar, corregir o detener una iniciativa.

La skill diferencia hechos, interpretaciones, supuestos y recomendaciones. No inventa datos, benchmarks, atribución, testimonios ni resultados.

## Estructura del repositorio

```text
senior-marketing-professional/
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── measurement.md
```

### `SKILL.md`

Es el archivo principal y obligatorio de la skill. Contiene:

- El nombre y la descripción que Codex utiliza para reconocer cuándo debe activarla.
- El enfoque profesional y los criterios de decisión.
- Los modos de trabajo: estrategia, go-to-market, campañas, auditoría, marca, contenidos, lifecycle, CRM y reportes.
- Las reglas de priorización y calidad.
- Los límites de autorización antes de publicar, enviar mensajes o modificar campañas, presupuestos, segmentaciones o registros.

Codex carga este archivo cuando la solicitud coincide con la descripción de la skill o cuando se invoca explícitamente.

### `agents/openai.yaml`

Contiene metadatos para la interfaz de Codex. Define:

- El nombre visible de la skill.
- Su descripción corta.
- Un prompt inicial sugerido.

Este archivo no contiene conocimiento de marketing ni reemplaza a `SKILL.md`. Su función principal es presentar la skill correctamente en la interfaz.

### `references/measurement.md`

Es una referencia especializada que se consulta únicamente cuando la tarea requiere medición, atribución, presupuestos, forecasting o experimentación.

Incluye orientación sobre:

- Métricas de negocio, comportamiento y marketing.
- CAC, ROAS, LTV, conversión y velocidad del pipeline.
- Definiciones, fuentes y ventanas temporales.
- Limitaciones de la atribución.
- Pruebas A/B, grupos de control e incrementalidad.
- Forecasts y escenarios sin falsa precisión.

Separar esta información permite que Codex cargue el contenido técnico solo cuando resulta necesario.

## Instalación

### Windows con PowerShell

```powershell
git clone git@github.com:Taoista/senior-marketing-professional-skill.git "$env:USERPROFILE\.codex\skills\senior-marketing-professional"
```

### macOS o Linux

```bash
git clone git@github.com:Taoista/senior-marketing-professional-skill.git ~/.codex/skills/senior-marketing-professional
```

También puedes utilizar HTTPS:

```bash
git clone https://github.com/Taoista/senior-marketing-professional-skill.git ~/.codex/skills/senior-marketing-professional
```

Después de instalarla, inicia un chat o una sesión nueva para que Codex detecte la skill.

## Cómo usarla

Puedes invocarla explícitamente escribiendo:

```text
$senior-marketing-professional
```

También puede activarse automáticamente cuando la solicitud corresponde a su descripción.

### Ejemplo: estrategia

```text
$senior-marketing-professional Crea una estrategia de marketing para una empresa
B2B SaaS que quiere aumentar su pipeline calificado durante los próximos seis meses.
Separa hechos, supuestos y recomendaciones.
```

### Ejemplo: campaña

```text
$senior-marketing-professional Diseña el brief de una campaña para lanzar este
producto en Chile. Define audiencia, comportamiento esperado, promesa, prueba,
mensajes, canales, presupuesto, responsables y medición.
```

### Ejemplo: auditoría

```text
$senior-marketing-professional Revisa estos resultados de marketing, identifica
el principal cuello de botella y prioriza tres intervenciones. Explica la evidencia,
los riesgos y cómo medir cada intervención.
```

### Ejemplo: reporte ejecutivo

```text
$senior-marketing-professional Convierte estos datos en un reporte ejecutivo.
Explica qué cambió, por qué podría haber cambiado, el impacto comercial,
el nivel de confianza y las decisiones que debe tomar la dirección.
```

## Información útil para obtener mejores resultados

Cuando esté disponible, proporciona:

- Modelo de negocio y oferta.
- Mercado y geografía.
- Cliente objetivo.
- Objetivo comercial.
- Presupuesto y plazo.
- Canales actuales.
- Resultados históricos.
- Restricciones legales, operativas o de marca.
- Responsable de la decisión.

Si faltan datos importantes, la skill preguntará solo por aquello que pueda cambiar materialmente la recomendación. Cuando sea posible avanzar, utilizará supuestos explícitos.

## Seguridad y autorizaciones

La skill puede analizar información y preparar borradores, pero eso no autoriza automáticamente a:

- Publicar contenidos.
- Enviar comunicaciones.
- Cambiar presupuestos.
- Modificar segmentaciones.
- Editar campañas o registros de CRM.
- Contactar clientes o prospectos.

Antes de realizar una acción externa, debe confirmarse la cuenta, audiencia, contenido, presupuesto, fecha y autoridad de aprobación.

## Personalización

Puedes adaptar la skill editando:

- `SKILL.md` para modificar criterios, procesos o alcance.
- `agents/openai.yaml` para cambiar el nombre visible o el prompt sugerido.
- `references/measurement.md` para incorporar métricas, fórmulas o políticas propias de la organización.

Mantén el valor `name: senior-marketing-professional` alineado con el nombre de la carpeta y con la invocación `$senior-marketing-professional`.
