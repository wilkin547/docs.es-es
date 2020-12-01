---
ms.openlocfilehash: 394f2daebad7b6af94bee4d7876796e87fe8ab19
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032065"
---
### <a name="handling-corrupted-state-exceptions-is-not-supported"></a>No se admite el control de excepciones de estado dañado

No se admite el control de excepciones de estado de proceso dañado en .NET Core.

#### <a name="change-description"></a>Descripción del cambio

Anteriormente, las excepciones de estado de proceso dañado podían detectarse y controlarse mediante controladores de excepciones de código administrado, por ejemplo, al usar una instrucción [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) en C#.

A partir de .NET Core 1.0, las excepciones de estado de proceso dañado no se pueden controlar mediante código administrado. Common Language Runtime no entrega las excepciones de estado de proceso dañado al código administrado.

#### <a name="version-introduced"></a>Versión introducida

1.0

#### <a name="recommended-action"></a>Acción recomendada

Para no tener que controlar las excepciones de estado de proceso dañado, aborde las situaciones que conducen a ellas. Si es absolutamente necesario controlar las excepciones de estado de proceso dañado, escriba el controlador de excepciones en código de C o C++.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>
- [Elemento legacyCorruptedStateExceptionsPolicy](~/docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)

<!--

#### Affected APIs

- `T:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute`

-->
