---
description: 'Palabra clave contextual remove: Referencia de C#'
title: 'Palabra clave contextual remove: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- remove_CSharpKeyword
helpviewer_keywords:
- remove event accessor [C#]
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
ms.openlocfilehash: a5514e72a04daa1232dbdf9a37813f09de791590
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136959"
---
# <a name="remove-c-reference"></a>remove (Referencia de C#)

La palabra clave contextual `remove` se usa para definir un descriptor de acceso de eventos personalizado que se invoca cuando el código de cliente cancela la suscripción a su [evento](event.md). Si proporciona un descriptor de acceso `remove` personalizado, también debe proporcionar un descriptor de acceso [add](add.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, se muestra un evento con descriptores de acceso [add](add.md) y `remove` personalizados. Para obtener el ejemplo completo, consulte [Procedimiento Implementar eventos de interfaz](../../programming-guide/events/how-to-implement-interface-events.md).

 [!code-csharp[csrefKeywordsContextual#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#15)]

Normalmente, no necesita proporcionar sus propios descriptores de acceso de eventos personalizados. Los descriptores de acceso que se generan automáticamente mediante el compilador cuando declara un evento son suficientes para la mayoría de escenarios.

## <a name="see-also"></a>Vea también

- [Eventos](../../programming-guide/events/index.md)
