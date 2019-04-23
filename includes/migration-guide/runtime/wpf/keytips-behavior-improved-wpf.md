---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805030"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Mejora del comportamiento de los KeyTip en WPF

|   |   |
|---|---|
|Detalles|El comportamiento de los KeyTip se ha modificado para equipararlo al de Microsoft Word y el Explorador de Windows. Mediante la comprobación de si el estado del KeyTip está habilitado o no cuando se presiona una <xref:System.Windows.Input.KeyEventArgs.SystemKey> (en concreto, <xref:System.Windows.Input.Key> o <xref:System.Windows.Input.Key.F11>), WPF administra las teclas de KeyTip de la forma adecuada. Los KeyTip ahora cierran un menú incluso cuando se abre con el mouse.|
|Sugerencia|N/D|
|Ámbito|Borde|
|Versión|4.7.2|
|Tipo|Tiempo de ejecución|
