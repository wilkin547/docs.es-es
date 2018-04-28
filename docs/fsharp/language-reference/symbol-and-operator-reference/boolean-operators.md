---
title: Operadores booleanos (F#)
description: 'Obtenga información acerca de los operadores booleanos que están disponibles en el lenguaje de programación de F #.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0b11b5133b02b6f507c7886b2fbaebf30abf46cb
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="boolean-operators"></a>Operadores booleanos

En este tema se describe la compatibilidad con los operadores booleanos en el lenguaje F #.


## <a name="summary-of-boolean-operators"></a>Resumen de operadores booleanos
En la tabla siguiente se resume los operadores booleanos que están disponibles en el lenguaje F #. Es el único tipo admitido por estos operadores el `bool` tipo.

|Operador|Descripción|
|--------|-----------|
|`not`|Negación booleana|
|<code>&#124;&#124;</code>|OR booleano|
|`&&`|AND booleano|

Realizan el booleano operadores AND y OR *evaluación cortocircuitada*, es decir, evalúan la expresión situada a la derecha del operador sólo cuando sea necesario determinar el resultado general de la expresión. La segunda expresión de la `&&` operador se evalúa solo si la primera expresión se evalúa como `true`; la segunda expresión de la `||` operador se evalúa solo si la primera expresión se evalúa como `false`.

## <a name="see-also"></a>Vea también
[Operadores bit a bit](bitwise-operators.md)

[Operadores aritméticos](arithmetic-operators.md)

[Referencia de símbolos y operadores](index.md)
