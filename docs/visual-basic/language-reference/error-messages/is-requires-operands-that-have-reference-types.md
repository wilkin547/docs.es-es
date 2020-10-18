---
title: "'Is' requiere operandos que tienen tipos de referencia, pero este operando tiene el tipo de valor '<typename>'"
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: 5c9f156272cd0c3cbaeadbc0e162129f41619cc6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163355"
---
# <a name="bc30020-is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a>BC30020: ' is ' requiere operandos que tengan tipos de referencia, pero este operando tiene el tipo de valor ' \<typename> '

El `Is` operador de comparación determina si dos variables de objeto hacen referencia a la misma instancia. Esta comparación no está definida para los tipos de valor.

 **Identificador de error:** BC30020

## <a name="to-correct-this-error"></a>Para corregir este error

- Utilice el operador de comparación aritmética adecuado o el `Like` operador para comparar dos tipos de valor.

## <a name="see-also"></a>Vea también

- [Operador Is](../operators/is-operator.md)
- [Like (Operador)](../operators/like-operator.md)
- [Operadores de comparación](../operators/comparison-operators.md)
