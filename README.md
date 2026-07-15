# Repositorio de Altas – Carga Masiva Brosys / Vida Cámara

Repositorio **HTML autocontenido** para transcribir y **acumular** formularios de incorporación (PDF) al
formato de **carga masiva "Altas"** de Brosys / Vida Cámara. Todo funciona en el navegador, sin backend.

---

## 🚀 Cómo publicar en GitHub Pages
1. Crea un repositorio nuevo en GitHub (ej. `repositorio-altas-brosys`) y márcalo **Public**.
2. Haz clic en **"Add file" → "Upload files"** y sube el contenido de este paquete (`index.html`, `README.md`, `.gitignore`, carpeta `data/`).
3. **Commit changes**.
4. Ve a **Settings → Pages**.
5. En *Build and deployment → Source*, elige **"Deploy from a branch"**, rama `main`, carpeta `/ (root)` y pulsa **Save**.
6. Espera ~1 minuto. Tu URL pública será: `https://<usuario>.github.io/<repo>/`

> Como el archivo se llama `index.html`, GitHub Pages lo abre automáticamente.

---

## 💻 Uso local
Solo haz **doble clic en `index.html`** y se abrirá en tu navegador. Los datos ingresados se guardan
en el **localStorage** del navegador, por lo que se conservan al recargar la página.

---

## ✨ Funcionalidades
- 📊 **Panel de estadísticas**: registros totales, titulares únicos, pólizas Vida (T) y pólizas con carga (T+C).
- ➕ **Agregar formulario manual** con los **32 campos** y listas validadas (Tipo Movimiento, Sexo, Tipo Cuenta y Banco según el instructivo).
- ⬆️ **Importar CSV/Excel** (carga en lote; Excel vía SheetJS).
- ⬇️ **Exportar a Excel (.xlsx)** y **Exportar CSV**.
- 📄 **Arrastrar y soltar PDF**: lectura local con PDF.js; **precarga el modal** para que revises y confirmes antes de guardar.
- 🔎 **Buscador en vivo** y 🗑 **borrado por fila**.
- 💾 **Persistencia** en localStorage.

---

## 📋 Formato de columnas (32)
```
Rut Titular, Nombres, Apellido Paterno, Apellido Materno, Sexo, Fecha Nacimiento,
Tipo Movimiento, Telefono, Email, Poliza, Numero Grupo, Fecha Inicio, Capital, Renta,
Peso, Estatura, Pre exisstencia, Sucursal, Area, Cargo, Banco, Tipo Cuenta, Numero Cuenta,
Rut Carga, Nombre Carga, Apellido Paterno Carga, Apellido Materno Carga, Rol Carga,
Sexo Carga, Fecha Nacimiento Carga, Fecha Inicio Vigencia Carga, Fecha Solicitud
```

---

## 📏 Reglas del instructivo aplicadas
- **RUT** completo, **sin puntos ni guión**.
- **Nombres y apellidos** en **MAYÚSCULAS y sin tildes** (Ñ → N).
- **Sexo**: `F` o `M`.
- **Fechas** en formato `dd-mm-aaaa`.
- **Banco** y **Tipo de Cuenta**: se usa el **NOMBRE tal cual** aparece en el instructivo (no el código).
- Campos sin dato → `Sin info` o **en blanco** según corresponda.
- **Cada póliza en una fila** distinta.
- En **póliza de Vida** solo va `T` (no lleva carga).
- **Capital/Renta** = `0` si no aplica.

---

## ⚠️ Datos por confirmar
- **Números de póliza** y **fechas de vigencia**: marcados como `POR CONFIRMAR`.
- **Naivys Torres**: el banco `MERCADO PAGO` **no existe** en la hoja "Códigos bancarios" → dejado en blanco.
- **Karen Peña**: **banco y N° de cuenta en blanco** en el formulario; **año de firma** (`26-06-20`) a confirmar (interpretado como 2026).

---

## 🌐 Dependencias (CDN)
- **SheetJS (xlsx)** → para importar/exportar Excel.
- **PDF.js** → para leer los PDF arrastrados.

Requieren conexión a internet. **Sin conexión** siguen funcionando: ingreso manual, importar/exportar **CSV**, buscador y persistencia.

---

## 📂 Estructura del proyecto
```
.
├── index.html
├── README.md
├── .gitignore
└── data/
    └── plantilla_remesa_altas_REPOSITORIO.xlsx
```

---

> **Aviso de confidencialidad:** este paquete incluye datos de ejemplo (Naivys Torres, Karen Peña) como semilla.
> Contienen **datos personales**; trátalos con la debida confidencialidad y conforme a la normativa de protección de datos.
