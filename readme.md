# Calculadora de Finiquito Falck

Herramienta web interactiva elaborada por la **Sección Sindical de CCOO UTE La Pau Direxis Salut - Vallès Occidental**. Su objetivo es proporcionar una estimación aproximada del finiquito (liquidación bruta) correspondiente a la subrogación de los trabajadores de Falck.

## Funcionalidades y Conceptos Soportados

La aplicación permite calcular el finiquito de manera personalizada introduciendo los siguientes datos:

1. **Categoría Profesional:**
   - Permite seleccionar entre *TES Conductor*, *TES Ayudante* o *TES Portalliteras*. Cada categoría cuenta con valores específicos de salario base, complemento de formación y precio de hora ordinaria.
2. **Antigüedad (Trienios):**
   - Configurable de 0 a 7 trienios. Influye en el plus de antigüedad y en el precio de la hora ordinaria (extra).
3. **Vacaciones Disfrutadas:**
   - Días de vacaciones ya tomados (0, 9 o 15 días) para restar de los días generados en el periodo acumulado.
4. **Sección Especial (Bajas e IT):**
   - **Días de baja por IT:** Afectan proporcionalmente al devengo de la paga extra de invierno.
   - **Vacaciones pendientes de 2025:** Días acumulados que se sumarán al total de vacaciones a liquidar.
5. **Conceptos Variables:**
   - **Horas ordinarias (extras):** Multiplicadas por el precio de hora correspondiente a la categoría y trienio del trabajador.
   - **Horas domingo:** Multiplicadas por **0,61 €**.
   - **Horas festivo no local (24/06):** Multiplicadas por **3,11 €**.
   - **Horas nocturnas:** Multiplicadas por **0,83 €** (nuevo concepto añadido).

## Desglose del Cálculo

La calculadora realiza los cálculos en bruto y muestra un desglose detallado con fórmulas interactivas:
- **Paga Extra Invierno:** Proporcional a los días de alta (175 días de devengo menos los días de IT).
- **Vacaciones no disfrutadas:** Valor del día calculado a partir del salario base, complemento de formación, trienios y plus de asistencia, multiplicado por los días pendientes a liquidar.
- **Detalle de Variables:** Sumatorio de todas las horas extras y especiales declaradas.
- **A cuenta convenio:** Incremento del **4,04%** aplicado provisionalmente sobre la suma de la paga extra, vacaciones y variables.
- **Total Estimado:** Suma total de los conceptos en bruto.

## Requisitos y Cómo Ejecutar

El proyecto es una aplicación web estática pura (HTML, CSS con Tailwind CDN y JavaScript).

### Ejecución Local
Simplemente abre el archivo `index.html` en cualquier navegador web moderno. No requiere compilación ni servidores backend.

### Despliegue con Wrangler (Cloudflare Pages)
El proyecto está configurado para desplegarse mediante Cloudflare:
```bash
# Para ejecutar en un entorno de desarrollo local con wrangler
npx wrangler dev

# Para publicar en Cloudflare Pages
npx wrangler deploy
```