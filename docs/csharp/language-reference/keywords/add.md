---
title: 'add: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- add_CSharpKeyword
helpviewer_keywords:
- add event accessor [C#]
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
ms.openlocfilehash: 1cf82e3d048e465d533e87dc639a13071b41544a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606041"
---
# <a name="add-c-reference"></a>add (Referencia de C#)
La palabra clave contextual `add` se usa para definir un descriptor de acceso de eventos personalizado que se invoca cuando el código de cliente se suscribe a su [evento](./event.md). Si proporciona un descriptor de acceso `add` personalizado, también debe proporcionar un descriptor de acceso [remove](./remove.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un evento que tiene descriptores de acceso `add` y [remove](./remove.md) personalizados. Para obtener el ejemplo completo, vea [Cómo:  Implementar eventos de interfaz](../../programming-guide/events/how-to-implement-interface-events.md).  
  
[!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]
  
 Normalmente, no necesita proporcionar sus propios descriptores de acceso de eventos personalizados. Los descriptores de acceso que se generan automáticamente mediante el compilador cuando declara un evento son suficientes para la mayoría de escenarios.  
  
## <a name="see-also"></a>Vea también

- [Eventos](../../programming-guide/events/index.md)
