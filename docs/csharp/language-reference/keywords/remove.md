---
title: 'Palabra clave contextual remove: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: b5c604cbb0fef158750b0fa487374ab293795fc7
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633720"
---
# <a name="remove-c-reference"></a>remove (Referencia de C#)

La palabra clave contextual `remove` se usa para definir un descriptor de acceso de eventos personalizado que se invoca cuando el código de cliente cancela la suscripción a su [evento](event.md). Si proporciona un descriptor de acceso `remove` personalizado, también debe proporcionar un descriptor de acceso [add](add.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, se muestra un evento con descriptores de acceso [add](add.md) y `remove` personalizados. Para obtener el ejemplo completo, vea [Cómo:  Implementar eventos de interfaz](../../programming-guide/events/how-to-implement-interface-events.md).

 [!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]

Normalmente, no necesita proporcionar sus propios descriptores de acceso de eventos personalizados. Los descriptores de acceso que se generan automáticamente mediante el compilador cuando declara un evento son suficientes para la mayoría de escenarios.

## <a name="see-also"></a>Vea también

- [Eventos](../../programming-guide/events/index.md)
