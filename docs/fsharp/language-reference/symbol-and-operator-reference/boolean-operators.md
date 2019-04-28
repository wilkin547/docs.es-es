---
title: Operadores booleanos
description: Obtenga información sobre los operadores booleanos que están disponibles en el F# lenguaje de programación.
ms.date: 05/16/2016
ms.openlocfilehash: 5353b6ec6a0bd610f3446761a1d28f01f0403302
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925819"
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