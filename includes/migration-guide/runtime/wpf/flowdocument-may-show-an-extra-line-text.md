---
ms.openlocfilehash: 6c1740df66ead271afa5f97dc125587810946bc6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379697"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a>FlowDocument puede mostrar una línea de texto adicional

|   |   |
|---|---|
|Detalles|En algunos casos, un elemento <xref:System.Windows.Documents.FlowDocument> mostrará una línea de texto adicional cuando se ejecuta en .NET Framework 4.5 en comparación a cómo se mostraba cuando se ejecutaba en .NET Framework 4.0. No hay casos conocidos de que el cambio provoque que un texto se muestre de forma incorrecta o ilegible, pero podría dar la impresión de que el texto se omitió anteriormente de la vista de un <xref:System.Windows.Documents.FlowDocument>.|
|Sugerencia|En algunos casos, reducir la propiedad PageHeight del elemento de visualización en uno puede restaurar el número anterior de líneas mostradas.|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Documents.FlowDocument.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor?displayProperty=nameWithType></li></ul>|
