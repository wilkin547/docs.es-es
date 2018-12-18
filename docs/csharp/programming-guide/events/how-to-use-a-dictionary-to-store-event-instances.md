---
title: 'Procedimiento Utilizar un diccionario para almacenar instancias de eventos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: 819c81aed3a6f09a20e51285058dcc77749dd33a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245147"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>Procedimiento Utilizar un diccionario para almacenar instancias de eventos (Guía de programación de C#)
Uno de los usos de `accessor-declarations` consiste en exponer numerosos eventos sin asignar un campo a cada evento, pero usando en su lugar un diccionario para almacenar las instancias del evento. Esto solo es útil si tiene muchos eventos, pero espera que la mayoría de ellos no se implemente.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideEvents#9](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-use-a-dictionary-to-store-event-instances_1.cs)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Eventos](../../../csharp/programming-guide/events/index.md)  
- [Delegados](../../../csharp/programming-guide/delegates/index.md)
