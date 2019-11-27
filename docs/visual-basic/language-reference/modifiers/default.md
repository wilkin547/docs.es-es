---
title: Default
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
ms.openlocfilehash: ad4c9528f208cc2c31f07b0506d1b049a7568c86
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351580"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Identifica una propiedad como la propiedad predeterminada de su clase, estructura o interfaz.  
  
## <a name="remarks"></a>Comentarios  
 Una clase, estructura o interfaz puede designar como máximo una de sus propiedades como la *propiedad predeterminada*, siempre que esa propiedad tome al menos un parámetro. Si el código hace referencia a una clase o estructura sin especificar un miembro, Visual Basic resuelve esa referencia a la propiedad predeterminada.  
  
 Las propiedades predeterminadas pueden dar lugar a una pequeña reducción en los caracteres de código fuente, pero pueden hacer que el código sea más difícil de leer. Si el código de llamada no está familiarizado con su clase o estructura, cuando hace referencia al nombre de la clase o de la estructura no puede estar seguro de si esa referencia tiene acceso a la clase o estructura, o a una propiedad predeterminada. Esto puede provocar errores del compilador o errores de lógica sutiles en tiempo de ejecución.  
  
 Puede reducir en cierto modo la posibilidad de que se produzcan errores de propiedad predeterminados Si usa siempre la [instrucción Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) para establecer la comprobación del tipo de compilador en `On`.  
  
 Si piensa utilizar una clase o estructura predefinida en el código, debe determinar si tiene una propiedad predeterminada y, en ese caso, cuál es su nombre.  
  
 Debido a estas desventajas, considere la posibilidad de no definir las propiedades predeterminadas. Para facilitar la lectura del código, también debe considerar la posibilidad de hacer referencia siempre a todas las propiedades explícitamente, incluso a las propiedades predeterminadas.  
  
 El modificador `Default` se puede usar en este contexto:  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
