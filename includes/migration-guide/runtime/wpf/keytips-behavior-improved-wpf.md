---
ms.openlocfilehash: 9659068304eb208fd6a0a753273453bc669fbc56
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621404"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Mejora del comportamiento de los KeyTip en WPF

#### <a name="details"></a>Detalles

El comportamiento de los KeyTip se ha modificado para equipararlo al de Microsoft Word y el Explorador de Windows. Mediante la comprobación de si el estado del KeyTip está habilitado o no cuando se presiona una <xref:System.Windows.Input.KeyEventArgs.SystemKey> (en concreto, <xref:System.Windows.Input.Key> o <xref:System.Windows.Input.Key.F11>), WPF administra las teclas de KeyTip de la forma adecuada. Los KeyTip ahora cierran un menú incluso cuando se abre con el mouse.

#### <a name="suggestion"></a>Sugerencia

N/D

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.7.2|
|Tipo|Tiempo de ejecución|
