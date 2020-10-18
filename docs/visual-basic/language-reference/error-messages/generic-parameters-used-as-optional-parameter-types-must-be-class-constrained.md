---
title: Los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 5e0d4eaf7557eb9a544a8845299f3d69dbb78486
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163225"
---
# <a name="bc32124-generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>BC32124: los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase

Se declara un procedimiento con un parámetro opcional que usa un parámetro de tipo que no está restringido para ser un tipo de referencia.

 Siempre debe proporcionar un valor predeterminado para cada parámetro opcional. Si el parámetro es de un tipo de referencia, el valor opcional debe ser `Nothing` , que es un valor válido para cualquier tipo de referencia. Sin embargo, si el parámetro es de un tipo de valor, ese tipo debe ser un tipo de datos elemental predefinido por Visual Basic. Esto se debe a que un tipo de valor compuesto, como una estructura definida por el usuario, no tiene ningún valor predeterminado válido.

 Cuando se usa un parámetro de tipo para un parámetro opcional, se debe garantizar que sea de un tipo de referencia para evitar la posibilidad de que se produzca un tipo de valor sin un valor predeterminado válido. Esto significa que debe restringir el parámetro de tipo con la `Class` palabra clave o con el nombre de una clase específica.

 **Identificador de error:** BC32124

## <a name="to-correct-this-error"></a>Para corregir este error

- Restrinja el parámetro de tipo para que acepte solo un tipo de referencia o no lo use para el parámetro opcional.

## <a name="see-also"></a>Vea también

- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Type List](../statements/type-list.md)
- [Instrucción Class](../statements/class-statement.md)
- [Parámetros opcionales](../../programming-guide/language-features/procedures/optional-parameters.md)
- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Nothing](../nothing.md)
