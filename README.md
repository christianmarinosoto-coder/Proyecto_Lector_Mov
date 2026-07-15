# Repositorio de Altas – Carga Masiva Brosys / Vida Cámara

Aplicación HTML autocontenida para transcribir y **acumular** formularios de incorporación (PDF) al formato de **carga masiva "Altas"** de Brosys / Vida Cámara.

## 🚀 Cómo publicar en GitHub Pages
1. Crea un repositorio (público o privado) y sube estos archivos.
2. Ve a **Settings → Pages**.
3. En *Build and deployment → Source* elige **Deploy from a branch**.
4. Selecciona la rama `main` y la carpeta `/ (root)` y pulsa **Save**.
5. Espera ~1 minuto: tu URL será `https://<usuario>.github.io/<repo>/`.

> El archivo principal es `index.html`, GitHub Pages lo abre automáticamente.

## 💻 Uso local
Haz doble clic en `index.html` para abrirlo en el navegador. Los datos se guardan en el `localStorage` del navegador y sobreviven a recargas.

## ✨ Funcionalidades
- Panel de estadísticas: registros totales, titulares únicos, pólizas Vida (T), pólizas con carga (T+C).
- **Botón "Cargar PDF"** que despliega una zona de arrastrar-y-soltar; el PDF se procesa **localmente** con PDF.js y precarga el formulario para revisión.
- Agregar formulario manual con los 32 campos y listas validadas (Tipo Movimiento, Sexo, Tipo Cuenta, Banco según instructivo).
- Importar CSV/Excel y exportar a Excel (.xlsx) y CSV.
- Buscador en vivo, borrado por fila y persistencia en `localStorage`.

## 📋 Formato de columnas (32)
```
Rut Titular, Nombres, Apellido Paterno, Apellido Materno, Sexo, Fecha Nacimiento,
Tipo Movimiento, Telefono, Email, Poliza, Numero Grupo, Fecha Inicio, Capital, Renta,
Peso, Estatura, Pre exisstencia, Sucursal, Area, Cargo, Banco, Tipo Cuenta, Numero Cuenta,
Rut Carga, Nombre Carga, Apellido Paterno Carga, Apellido Materno Carga, Rol Carga,
Sexo Carga, Fecha Nacimiento Carga, Fecha Inicio Vigencia Carga, Fecha Solicitud
```

## 📏 Reglas del instructivo aplicadas
- RUT sin puntos ni guión.
- Nombres/apellidos en MAYÚSCULAS sin tildes (Ñ→N).
- Sexo F/M; fechas dd-mm-aaaa.
- Banco y Tipo de Cuenta con el NOMBRE tal cual del instructivo (no el código).
- Campos sin dato → "Sin info" o en blanco según corresponda.
- Cada póliza en una fila; en póliza de Vida solo va "T" (no lleva carga).
- Capital/Renta = 0 si no aplica.

## ⚠️ Datos por confirmar
- Números de póliza y fechas de vigencia marcados como "POR CONFIRMAR".
- Banco de Naivys ("MERCADO PAGO" no existe en códigos bancarios) y banco/cuenta de Karen en blanco.
- Año de firma de Karen (26-06-20) a confirmar.

## 🌐 Dependencias (CDN)
- SheetJS (xlsx) para exportar/importar Excel.
- PDF.js para lectura de PDF.
Requieren internet; sin conexión funcionan igual el ingreso manual, CSV, buscador y persistencia.

## 📂 Estructura del proyecto
```
index.html
README.md
.gitignore
data/plantilla_remesa_altas_REPOSITORIO.xlsx
```

---
_Datos de ejemplo (Naivys Torres, Karen Peña) incluidos como semilla. Contienen datos personales: tratar con confidencialidad._
