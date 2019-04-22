---
title: Default (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
ms.openlocfilehash: f78ffe42a9d618d44da2a50c0de831396576430c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836732"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Identifica una propiedad como propiedad predeterminada de su clase, estructura o interfaz.  
  
## <a name="remarks"></a>Comentarios  
 Puede designar una clase, estructura o interfaz a lo sumo uno de sus propiedades como el *propiedad predeterminada*, siempre que la propiedad tiene al menos un parámetro. Si el código hace referencia a una clase o estructura sin especificar a un miembro, Visual Basic resuelve que hacen referencia a la propiedad predeterminada.  
  
 Propiedades predeterminadas pueden producir una pequeña reducción en caracteres de código fuente, pero puede hacer que su código más difícil de leer. Si el código de llamada no está familiarizado con la clase o estructura, cuando realiza una referencia al nombre de clase o estructura no puede estar seguro si esa referencia tiene acceso a la clase o estructura en Sí o una propiedad predeterminada. Esto puede conducir a errores del compilador o errores sutiles tiempo de ejecución de lógica.  
  
 Algo puede reducir la posibilidad de errores de propiedad predeterminado al usar siempre el [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) para establecer el tipo de compilador para la comprobación `On`.  
  
 Si va a usar una clase o estructura en el código, debe determinar si tiene una propiedad predeterminada y si es así, lo que su nombre es.  
  
 Debido a estos inconvenientes, considere la posibilidad de no definir propiedades predeterminadas. Para mejorar la legibilidad de código, debe también tener en cuenta siempre referencia explícitamente a todas las propiedades, propiedades incluso predeterminadas.  
  
 El `Default` modificador se puede usar en este contexto:  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
