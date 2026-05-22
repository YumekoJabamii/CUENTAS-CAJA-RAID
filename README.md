# RAID — Panel de caja

App interna de RAID para gestionar clientes, cobros, gastos y caja mensual. Corre directo en el navegador, sin servidor ni instalación.

---

## Qué hace

- **Caja mensual** — ingresos esperados vs cobrados, gastos fijos, neto proyectado. Navegás mes a mes con las flechas.
- **Clientes** — cargás cada cliente una sola vez y aparece automáticamente en la caja y el calendario.
- **Gastos fijos** — suscripciones y gastos recurrentes que se suman a la caja todos los meses.
- **Únicos este mes** — cobros o gastos que aparecen solo en un mes puntual.
- **Calendario** — vista ordenada por día de cobro con avisos de facturación.

---

## Cómo usarla

1. Descargá el archivo `index.html`
2. Abrilo con cualquier navegador (Chrome, Firefox, Safari, Edge)
3. Listo — no necesita conexión a internet ni instalación

> Los datos se guardan automáticamente en el navegador cada 60 segundos. Si limpiás los datos del navegador, los datos se pierden — por eso existe el backup manual.

---

## Backup y exportación

### Backup JSON (recomendado antes de cualquier cambio)
Sidebar → **Exportar backup** → guarda un archivo `.json` con todos los datos.

Para restaurar: Sidebar → **Importar datos** → seleccionás el `.json`.

### Exportar a Excel
Sidebar → **Exportar a Excel** → genera un `.xlsx` con cuatro pestañas:
- **Clientes** — lista completa con montos, días de cobro y estado
- **Gastos fijos** — servicios mensuales con total
- **Caja mensual** — proyección de los últimos 3 meses y los próximos 8
- **Únicos** — cobros y gastos de un solo mes

---

## Flujo de trabajo recomendado

**Antes de pedir un cambio en el código:**
1. Exportar backup → guardar el `.json` en un lugar seguro
2. Reemplazar el `index.html` con la versión nueva
3. Importar datos → seleccionar el `.json` guardado

**Fin de mes:**
1. Exportar a Excel → guardar en Drive o carpeta local
2. Revisar que todos los cobros del mes estén marcados como confirmados

---

## Estructura del proyecto

```
/
└── index.html    — toda la app en un solo archivo (HTML + CSS + JS)
└── README.md     — este archivo
```

No hay dependencias que instalar. Las librerías externas (iconos y generación de Excel) se cargan desde CDN cuando hay conexión a internet.

Si la app se va a usar sin conexión, Moro puede descargar esas librerías y referenciarlas localmente.

---

## Librerías usadas

| Librería | Uso |
|----------|-----|
| [Tabler Icons](https://tabler.io/icons) | Íconos del sidebar y la UI |
| [SheetJS (xlsx)](https://sheetjs.com) | Generación del archivo Excel |

---

## Próximos pasos sugeridos

- [ ] Migrar datos de `localStorage` a una base de datos (Supabase recomendado) para sincronizar entre dispositivos
- [ ] Hacer el sidebar responsive para uso móvil (media queries)
- [ ] Agregar autenticación si se sube a un servidor compartido
- [ ] Historial de cobros confirmados por mes

---

## Desarrollado por

**RAID** — Desarrollo de software a medida para pymes.
CABA, Argentina.
