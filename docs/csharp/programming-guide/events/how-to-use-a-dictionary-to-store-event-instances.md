---
title: 'Procedimiento Utilizar un diccionario para almacenar instancias de eventos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 8f0284c5637890f35642346880d035619bc0e1e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560066"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Procedimiento Utilizar un diccionario para almacenar instancias de eventos (Guía de programación de C#)
Uno de los usos de `accessor-declarations` consiste en exponer numerosos eventos sin asignar un campo a cada evento, pero usando en su lugar un diccionario para almacenar las instancias del evento. Esto solo es útil si tiene muchos eventos, pero espera que la mayoría de ellos no se implemente.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Eventos](../../../csharp/programming-guide/events/index.md)
- [Delegados](../../../csharp/programming-guide/delegates/index.md)
