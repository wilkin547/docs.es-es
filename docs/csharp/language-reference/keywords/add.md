---
title: add (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: add_CSharpKeyword
helpviewer_keywords: add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cab77ad5a990cf85075455e347a4b1c02645af37
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2017
---
# <a name="add-c-reference"></a>add (Referencia de C#)
La palabra clave contextual `add` se usa para definir un descriptor de acceso de eventos personalizado que se invoca cuando el código de cliente se suscribe a su [evento](../../../csharp/language-reference/keywords/event.md). Si proporciona un descriptor de acceso `add` personalizado, también debe proporcionar un descriptor de acceso [remove](../../../csharp/language-reference/keywords/remove.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un evento que tiene descriptores de acceso `add` y [remove](../../../csharp/language-reference/keywords/remove.md) personalizados. Para obtener el ejemplo completo, vea [Cómo: Implementar eventos de interfaz](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
 [!code-csharp[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/add_1.cs)]  
  
 Normalmente, no necesita proporcionar sus propios descriptores de acceso de eventos personalizados. Los descriptores de acceso que se generan automáticamente mediante el compilador cuando declara un evento son suficientes para la mayoría de escenarios.  
  
## <a name="see-also"></a>Vea también  
 [Eventos](../../../csharp/programming-guide/events/index.md)
