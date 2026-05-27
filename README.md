# Calculadora Salarial CR

Herramienta web para el cálculo detallado de salarios en Costa Rica. Diseñada para trabajadores y profesionales de RRHH que necesitan entender con exactitud el impacto de las deducciones legales, los fondos de capitalización y las cargas patronales sobre un salario bruto mensual.

---

## Descripción

La aplicación toma un salario bruto mensual y produce un desglose completo de todos los flujos financieros que lo afectan: deducciones directas al trabajador, fondos generados a su nombre y cargas adicionales del patrono. El cálculo respeta la estructura legal vigente en Costa Rica, incluyendo los tramos progresivos del Impuesto sobre la Renta y las tasas de la Caja Costarricense de Seguro Social (CCSS).

El resultado se presenta por período de pago (quincenal o bisemanal), con visualizaciones gráficas y una tabla comparativa por escala salarial.

---

## Funcionalidades

### Cálculo de deducciones del trabajador

| Concepto | Tasa |
|---|---|
| CCSS – Seguro de Enfermedad y Maternidad (SEM) | 5.50% |
| CCSS – Invalidez, Vejez y Muerte (IVM) | 3.67% |
| Banco Popular y Desarrollo Comunal (BPDC) | 1.00% |
| Instituto Mixto de Ayuda Social (IMAS) | 0.50% |
| Impuesto sobre la Renta | Progresivo (0% – 25%) |
| Asociación Solidarista (aporte obrero) | Configurable |

### Tramos del Impuesto sobre la Renta (base neta de cargas)

| Tramo | Tasa |
|---|---|
| Hasta ₡929,000 | Exento |
| ₡929,001 – ₡1,362,000 | 10% |
| ₡1,362,001 – ₡2,414,000 | 15% |
| ₡2,414,001 – ₡4,830,000 | 20% |
| Más de ₡4,830,000 | 25% |

### Fondos de capitalización (ahorro futuro a nombre del trabajador)

- **FCL – Fondo de Capitalización Laboral:** 1.50% patronal, destinado a cesantía o retiro anticipado.
- **ROP – Régimen Obligatorio de Pensiones:** 3.17% patronal, acumulado en la Operadora de Pensiones del trabajador.

### Horas extra

Soporta dos modos de ingreso:

- **Manual:** cantidad de horas y tipo (ordinaria 1.5x o feriado/nocturna 2.0x).
- **Estimado por tipo de día:** separando horas en días normales y días feriados.

El valor de hora ordinaria puede ingresarse manualmente o calcularse automáticamente dividiendo el salario mensual entre 240 horas.

### Solidarismo

Permite configurar el porcentaje de aporte obrero (deducido del salario) y el aporte patronal de cesantía solidarista, mostrando ambos de forma diferenciada en el desglose.

### Módulo de incapacidades

Calcula el subsidio diario estimado en caso de incapacidad médica:

- Días 1 a 3: 50% del salario diario bruto, cubierto por el patrono.
- Día 4 en adelante: 60% del salario diario bruto, cubierto por la CCSS.

### Cargas patronales referenciales

Muestra el costo adicional que representa cada trabajador para el patrono, incluyendo SEM patronal, IVM patronal, Asignaciones Familiares, INS Riesgos del Trabajo y FODESAF/IMAS/INA.

### Análisis de punto de inflexión fiscal

Indica si el salario se encuentra en la zona exenta de renta o, si ya tributa, cuál es la tasa marginal activa y el margen disponible antes de cruzar al siguiente tramo.

---

## Visualizaciones

La herramienta incluye tres vistas gráficas sobre el período calculado:

- **Distribución (donut):** proporción entre neto líquido, deducciones, impuesto, solidarismo y fondos FCL/ROP.
- **Desglose (barras):** cascada de impacto entrada/salida desde el bruto hasta el neto.
- **Impacto por escala (líneas):** curva de cargas CCSS e impuesto de renta desde ₡400k hasta ₡4M mensuales.

Además, se genera una tabla comparativa que muestra el neto mensual y el porcentaje de retención total para distintos niveles salariales, resaltando el salario ingresado.

---

## Tecnologías utilizadas

- HTML5, CSS3 y JavaScript vanilla (sin frameworks)
- [Chart.js 4.4.1](https://www.chartjs.org/) para las visualizaciones
- Google Fonts: Syne, DM Mono, DM Sans
- Diseño responsivo adaptado a móvil, tablet y escritorio
- Compatible con PWA (manifest y meta tags para instalación en iOS y Android)

---

## Uso

No requiere instalación ni dependencias externas. Basta con abrir el archivo `index.html` en cualquier navegador moderno. Todos los cálculos se realizan del lado del cliente; no se envía ningún dato a servidores externos.

1. Ingresar el salario bruto mensual.
2. Seleccionar el período de pago (quincenal o bisemanal).
3. Completar los campos opcionales: horas extra, bono, solidarismo.
4. Presionar **Calcular salario**.

---

## Consideraciones legales

Las tasas utilizadas corresponden a la normativa laboral y tributaria de Costa Rica vigente al momento del desarrollo. Este proyecto es una herramienta de referencia informativa; para casos con implicaciones legales o fiscales, se recomienda consultar con un profesional en contabilidad o derecho laboral.

---

## Licencia

Este proyecto se distribuye sin garantías de ningún tipo. Puede usarse, modificarse y redistribuirse libremente para fines personales o educativos.
