---
description: 'Obtenga más información sobre: BC33000: la declaración del operador debe ser uno de los siguientes: +,-, *,,/, ^, &amp; , like, mod, and, or, XOR, not,  <<  >>...'
title: 'La declaración del operador debe ser uno de los siguientes: +,-, *,-,-, ^, &amp; , like, mod, and, or, XOR, not,  <<,  >>, =,  <>, <, <=, >, >=, ctype, IsTrue, IsFalse'
ms.date: 07/20/2015
f1_keywords:
- bc33000
- vbc33000
helpviewer_keywords:
- BC33000
ms.assetid: 15c5d8eb-3a8c-4141-8f41-33151afabf97
ms.openlocfilehash: 0ad82a6414387278622a10624952ebc35e7e9b83
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795565"
---
# <a name="bc33000-operator-declaration-must-be-one-of----amp-like-mod-and-or-xor-not--"></a>BC33000: la declaración del operador debe ser uno de los siguientes: +,-, *, \, /, ^, &amp; , like, mod, and, or, XOR, not, \<\<, >>...

Solo puede declarar un operador que sea válido para la sobrecarga. En la tabla siguiente se enumeran los operadores que se pueden declarar.

|Tipo|Operadores|
|----------|---------------|
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|Conversión (unaria)|`CType`|

 Tenga en cuenta que el `=` operador de la lista binaria es el operador de comparación, no el operador de asignación.

 **Identificador de error:** BC33000

## <a name="to-correct-this-error"></a>Para corregir este error

- Seleccione un operador del conjunto de operadores sobrecargables.

- Si necesita la función de sobrecarga de un operador que no se puede sobrecargar directamente, cree un procedimiento `Function` que tome los parámetros adecuados y devuelva el valor adecuado.

## <a name="see-also"></a>Vea también

- [Operator Statement](../statements/operator-statement.md)
- [Procedimientos de operador](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Procedimiento para definir un operador](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Procedimiento para definir un operador de conversión](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Instrucción Function](../statements/function-statement.md)
