---
title: El objeto o la clase no admite el conjunto de eventos
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 4a6f1f59f43cdb351d49fbcbfd18362db888586e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593209"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>El objeto o la clase no admite el conjunto de eventos
Se intentó usar un `WithEvents` variable con un componente que no puede funcionar como un origen de eventos para el conjunto de eventos especificado. Por ejemplo, desea recibir los eventos de un objeto, a continuación, cree otro objeto que `Implements` el primer objeto. Aunque podría pensar que podría recibir los eventos del objeto implementado, esto no es siempre el caso. `Implements` sólo implementa una interfaz para los métodos y propiedades. `WithEvents` no se admite para privada `UserControls`, porque el tipo de información necesaria para generar el `ObjectEvent` no está disponible en tiempo de ejecución.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  No puede recibir eventos para un componente que no del origen de eventos.  
  
## <a name="see-also"></a>Vea también  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)
