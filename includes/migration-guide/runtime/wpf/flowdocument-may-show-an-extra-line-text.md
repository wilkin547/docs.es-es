---
ms.openlocfilehash: a61005e317020c47a283dae292236624ec6057ce
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496803"
---
### <a name="flowdocument-may-show-an-extra-line-of-text"></a>FlowDocument puede mostrar una línea de texto adicional

#### <a name="details"></a>Detalles

En algunos casos, un elemento <xref:System.Windows.Documents.FlowDocument> mostrará una línea de texto adicional cuando se ejecuta en .NET Framework 4.5 en comparación a cómo se mostraba cuando se ejecutaba en .NET Framework 4.0. No hay casos conocidos de que el cambio provoque que un texto se muestre de forma incorrecta o ilegible, pero podría dar la impresión de que el texto se omitió anteriormente de la vista de un <xref:System.Windows.Documents.FlowDocument>.

#### <a name="suggestion"></a>Sugerencia

En algunos casos, reducir la propiedad PageHeight del elemento de visualización en uno puede restaurar el número anterior de líneas mostradas.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Documents.FlowDocument.%23ctor>
- <xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)>
- <xref:System.Windows.Controls.FlowDocumentReader.%23ctor>
- <xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor>
- <xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor>

<!--

#### Affected APIs

- `M:System.Windows.Documents.FlowDocument.#ctor`
- `M:System.Windows.Documents.FlowDocument.#ctor(System.Windows.Documents.Block)`
- `M:System.Windows.Controls.FlowDocumentReader.#ctor`
- `M:System.Windows.Controls.FlowDocumentPageViewer.#ctor`
- `M:System.Windows.Controls.Primitives.DocumentPageView.#ctor`

-->
