---
title: No se pudieron inferir los argumentos de tipo a partir del delegado
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: f7937a34ab425da684f892250884d21e020e4c57
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161249"
---
# <a name="bc36564-type-arguments-could-not-be-inferred-from-the-delegate"></a>BC36564: no se pudieron inferir los argumentos de tipo del delegado

Una instrucción de asignación usa `AddressOf` para asignar la dirección de un procedimiento genérico a un delegado, pero no proporciona ningún argumento de tipo al procedimiento genérico.

 Normalmente, cuando se invoca un tipo genérico, se facilita un argumento de tipo para cada parámetro de tipo que define el tipo genérico. Si no se facilita ningún argumento de tipo, el compilador intenta inferir los tipos que se deben pasar a los parámetros de tipo. Si el contexto no proporciona suficiente información para que el compilador infiera los tipos, se genera un error.

 **Identificador de error:** BC36564

## <a name="to-correct-this-error"></a>Para corregir este error

- Especifique los argumentos de tipo para el procedimiento genérico en la expresión `AddressOf` .

## <a name="see-also"></a>Vea también

- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Operador AddressOf](../operators/addressof-operator.md)
- [Generic Procedures in Visual Basic](../../programming-guide/language-features/data-types/generic-procedures.md)
- [Type List](../statements/type-list.md)
- [Métodos de extensión](../../programming-guide/language-features/procedures/extension-methods.md)
