---
title: Valor predeterminado
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
ms.openlocfilehash: 0c2808795d6fcbad7892369fd7f460ebf0406093
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372977"
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Identifica una propiedad como la propiedad predeterminada de su clase, estructura o interfaz.  
  
## <a name="remarks"></a>Observaciones  
 Una clase, estructura o interfaz puede designar como máximo una de sus propiedades como la *propiedad predeterminada*, siempre que esa propiedad tome al menos un parámetro. Si el código hace referencia a una clase o estructura sin especificar un miembro, Visual Basic resuelve esa referencia a la propiedad predeterminada.  
  
 Las propiedades predeterminadas pueden dar lugar a una pequeña reducción en los caracteres de código fuente, pero pueden hacer que el código sea más difícil de leer. Si el código de llamada no está familiarizado con su clase o estructura, cuando hace referencia al nombre de la clase o de la estructura no puede estar seguro de si esa referencia tiene acceso a la clase o estructura, o a una propiedad predeterminada. Esto puede provocar errores del compilador o errores de lógica sutiles en tiempo de ejecución.  
  
 Puede reducir en cierta medida la posibilidad de que se produzcan errores de propiedad predeterminados Si usa siempre la [instrucción Option Strict](../statements/option-strict-statement.md) para establecer la comprobación del tipo de compilador en `On` .  
  
 Si piensa utilizar una clase o estructura predefinida en el código, debe determinar si tiene una propiedad predeterminada y, en ese caso, cuál es su nombre.  
  
 Debido a estas desventajas, considere la posibilidad de no definir las propiedades predeterminadas. Para facilitar la lectura del código, también debe considerar la posibilidad de hacer referencia siempre a todas las propiedades explícitamente, incluso a las propiedades predeterminadas.  
  
 El `Default` modificador se puede usar en este contexto:  
  
 [Property Statement](../statements/property-statement.md)  
  
## <a name="see-also"></a>Consulte también

- [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)
- [Palabras clave](../keywords/index.md)
