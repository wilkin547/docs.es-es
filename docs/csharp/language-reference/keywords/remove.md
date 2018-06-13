---
title: remove (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: 16a169ce1a0ef5dbc29739b2d808acb19737669e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269124"
---
# <a name="remove-c-reference"></a>remove (Referencia de C#)
La palabra clave contextual `remove` se usa para definir un descriptor de acceso de eventos personalizado que se invoca cuando el código de cliente cancela la suscripción a su [evento](../../../csharp/language-reference/keywords/event.md). Si proporciona un descriptor de acceso `remove` personalizado, también debe proporcionar un descriptor de acceso [add](../../../csharp/language-reference/keywords/add.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, se muestra un evento con descriptores de acceso [add](../../../csharp/language-reference/keywords/add.md) y `remove` personalizados. Para obtener el ejemplo completo, vea [Cómo: Implementar eventos de interfaz](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 Normalmente, no necesita proporcionar sus propios descriptores de acceso de eventos personalizados. Los descriptores de acceso que se generan automáticamente mediante el compilador cuando declara un evento son suficientes para la mayoría de escenarios.  
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../csharp/programming-guide/events/index.md)
