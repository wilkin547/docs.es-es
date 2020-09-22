---
title: El objeto o la clase no admite el conjunto de eventos
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: e55a5515d88bd2782e31fdea7c07e16c595d43b5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873656"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>El objeto o la clase no admite el conjunto de eventos

Ha intentado usar una `WithEvents` variable con un componente que no puede funcionar como un origen de eventos para el conjunto de eventos especificado. Por ejemplo, desea recibir los eventos de un objeto y, a continuación, crear otro objeto que sea `Implements` el primer objeto. Aunque podría pensar que podría recibir los eventos del objeto implementado, este no es siempre el caso. `Implements` solo implementa una interfaz para los métodos y las propiedades. `WithEvents` no se admite para Private `UserControls` , porque la información de tipo necesaria para generar `ObjectEvent` no está disponible en tiempo de ejecución.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. No se pueden recibir eventos para un componente que no tiene eventos de origen.  
  
## <a name="see-also"></a>Consulte también

- [WithEvents](../modifiers/withevents.md)
- [Implements (Instrucción)](../statements/implements-statement.md)
