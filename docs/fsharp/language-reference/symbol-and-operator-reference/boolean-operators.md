---
title: Operadores booleanos (F#)
description: "Obtenga información acerca de los operadores booleanos que están disponibles en el lenguaje de programación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
