# Google Apps Script - PRODUCCION NOCTURNA

1. Crea o abre el Google Sheet de PRODUCCION NOCTURNA.
2. Si duplicaste el Sheet de Candelaria, deja intactas estas hojas de catalogo: PRODUCTOS, DESTINO, MOTIVOS MERMA, FACTORES y RECETAS.
3. En la copia nocturna, vacia solo los datos guardados de REGISTROS RECETAS, ENTREGADO y MERMA, dejando la fila 1 con encabezados.
4. Ve a Extensiones > Apps Script.
5. Sustituye el codigo por el contenido de Code.gs de este proyecto.
6. En Code.gs, cambia PEGAR_ID_DEL_SHEET_NOCTURNA_AQUI por el ID del Google Sheet nocturno.
7. Guarda y despliega como Web App.
8. Copia la URL del deployment y pegala en index.html.

## Hojas requeridas
- REGISTROS RECETAS
- PRODUCTOS
- RECETAS
- DESTINO
- ENTREGADO
- MERMA
- MOTIVOS MERMA

## Mapeo de columnas en REGISTROS RECETAS
- Marca Temporal
- Fecha
- Codigos
- Productos
- Unidades
- Receta
- Responsable

## Mapeo de columnas en ENTREGADO
- Marca Temporal
- Fecha
- Codigos
- Productos
- Unidad
- Cantidad
- Destino
- Responsable

## Mapeo de columnas en MERMA
- Marca Temporal
- Fecha
- Codigos
- Productos
- Unidad
- Cantidad
- Motivo de la Merma
- Responsable

## Catalogos
- PRODUCTOS: columna A = codigo, columna B = descripcion, columna C = UM.
- RECETAS: columna A = nombre de receta.
- DESTINO: columna A = nombre de destino.
- MOTIVOS MERMA: columna A = motivo de merma.

## Endpoint disponibles
- GET ?action=getCatalogs
- POST action=createReceta
- POST action=createEntregado
- POST action=createMerma

## Flujo de envio por modulo
- RECETAS: Fecha y Responsable fijos por envio; items con Codigo + Receta.
- ENTREGADO: Fecha y Responsable fijos por envio; items con Codigo + Cantidad + Destino.
- MERMA: Fecha y Responsable fijos por envio; items con Codigo + Cantidad + Motivo de la Merma.
