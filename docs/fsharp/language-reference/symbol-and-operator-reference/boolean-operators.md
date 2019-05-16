---
title: Operadores booleanos
description: Obtenga información sobre los operadores booleanos que están disponibles en el F# lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: ad4bdd1121389f7e280647dbe0c4d0098ffb17df
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641894"
---
# <a name="boolean-operators"></a>Operadores booleanos

Este tema describe la compatibilidad con los operadores booleanos en la F# lenguaje.

## <a name="summary-of-boolean-operators"></a>Resumen de operadores booleanos

En la tabla siguiente se resume los operadores booleanos que están disponibles en el F# lenguaje. Es el único tipo admitido por estos operadores el `bool` tipo.

|Operador|Descripción|
|--------|-----------|
|`not`|Negación booleana|
|<code>&#124;&#124;</code>|OR booleano|
|`&&`|AND Boolean|

Realizan el booleano operadores AND y OR *la evaluación de cortocircuito*, es decir, evalúa la expresión a la derecha del operador solo cuando sea necesario determinar el resultado global de la expresión. La segunda expresión de la `&&` operador se evalúa solo si la primera expresión se evalúa como `true`; la segunda expresión de la `||` operador se evalúa solo si la primera expresión se evalúa como `false`.

## <a name="see-also"></a>Vea también

- [Operadores bit a bit](bitwise-operators.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Referencia de símbolos y operadores](index.md)
