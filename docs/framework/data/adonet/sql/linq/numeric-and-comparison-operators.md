---
description: 'Más información sobre: Operadores numéricos y de comparación'
title: Operadores numéricos y de comparación
ms.date: 03/30/2017
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
ms.openlocfilehash: 5b17f19769436ac4e575ac974668eadc3b17b8f6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99695533"
---
# <a name="numeric-and-comparison-operators"></a>Operadores numéricos y de comparación

Los operadores aritméticos y de comparación funcionan como cabía esperar en Common Language Runtime (CLR), con las siguientes excepciones:

- SQL no admite al operador de módulo en números de punto flotante.

- SQL no admite la aritmética no comprobada.

- Los operadores de incremento y decremento producen efectos no deseados cuando se utilizan en expresiones que no se pueden replicar en SQL y son, por tanto, incompatibles.

## <a name="supported-operators"></a>Operadores admitidos

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite los operadores siguientes.

- Operadores aritméticos básicos:

  - `+`

  - `-` (resta)

  - `*`

  - `/`

  - División de enteros en Visual Basic (`\`)

  - `%` (Visual Basic `Mod`)

  - `<<`

  - `>>`

  - `-` (negación unaria)

- Operadores de comparación básicos:

  - `=` en Visual Basic y `==` en C#

  - `<>` en Visual Basic y `!=` en C#

  - `Is/IsNot` en Visual Basic

  - `<`

  - `<=`

  - `>`

  - `>=`

## <a name="see-also"></a>Vea también

- [Tipos de datos y funciones](data-types-and-functions.md)
- [Operadores de C#](../../../../../csharp/language-reference/operators/index.md)
- [Operadores](../../../../../visual-basic/language-reference/operators/index.md)
