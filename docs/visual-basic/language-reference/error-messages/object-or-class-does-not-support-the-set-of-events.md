---
title: El objeto o la clase no admite el conjunto de eventos
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 2e00bdd624b54e19f19b6dabf6681bbf89709e60
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822588"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>El objeto o la clase no admite el conjunto de eventos
Se intentó usar un `WithEvents` variable con un componente que no puede funcionar como un origen de eventos para el conjunto de eventos especificado. Por ejemplo, desea recibir los eventos de un objeto y, después, cree otro objeto que `Implements` el primer objeto. Aunque es posible que cree que puede recibir los eventos del objeto implementado, esto no es siempre el caso. `Implements` solo se implementa una interfaz para los métodos y propiedades. `WithEvents` no se admite para privada `UserControls`, porque el tipo de información necesaria para generar el `ObjectEvent` no está disponible en tiempo de ejecución.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  No puede recibir eventos para un componente que no del origen de eventos.  
  
## <a name="see-also"></a>Vea también

- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
- [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md)
