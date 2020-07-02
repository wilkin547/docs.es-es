---
ms.openlocfilehash: d78d083b16ac034c6c393dbc0f6094ee4c6c63c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622383"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel.BringIndexIntoView inicia una excepción ArgumentOutOfRangeException

#### <a name="details"></a>Detalles

<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> funcionará de forma asíncrona cuando se habilite la virtualización de columnas pero el ancho de las columnas todavía no se haya determinado.  Si se quitan las columnas antes de que se complete la operación asíncrona, se puede iniciar una excepción <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>.

#### <a name="suggestion"></a>Sugerencia

Siga uno de estos pasos:<ol><li>Actualice a .NET Framework 4.7.</li><li>Instale la revisión de reparación más reciente para .NET Framework 4.6.2.</li><li>Evite quitar las columnas hasta que se haya completado la respuesta asíncrona para <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</li></ol>

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
