---
title: Default (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Default
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- default properties, in Visual Basic
- Default keyword [Visual Basic]
- default properties
ms.assetid: 45fce9b9-d212-4b2d-ab86-6e359b8b57af
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18126a0a5b6254da0b43e806b3de1f5b2127e6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="default-visual-basic"></a>Default (Visual Basic)
Identifica una propiedad como la propiedad predeterminada de su clase, estructura o interfaz.  
  
## <a name="remarks"></a>Comentarios  
 Una clase, estructura o interfaz puede designar al menos uno de sus propiedades como el *propiedad predeterminada*, siempre que la propiedad tiene al menos un parámetro. Si el código hace referencia a una clase o estructura sin especificar a un miembro, Visual Basic resuelve que hacen referencia a la propiedad predeterminada.  
  
 Propiedades predeterminadas pueden producir una pequeña reducción en caracteres de código fuente, pero puede hacer que el código más difícil de leer. Si el código de llamada no está familiarizado con la clase o estructura, cuando hace referencia al nombre de clase o estructura no podrá saber si esa referencia tiene acceso a la clase o estructura en Sí o una propiedad predeterminada. Esto puede conducir a errores del compilador o errores sutiles lógicos de tiempo de ejecución.  
  
 Algo puede reducir la posibilidad de errores de propiedades de forma predeterminada al usar siempre el [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md) para establecer el tipo de compilador comprobación `On`.  
  
 Si planea usar una clase o estructura en el código, debe determinar si tiene una propiedad predeterminada y si es así, lo que su nombre es.  
  
 Debido a estas desventajas, considere la posibilidad de no definir propiedades predeterminadas. Para la legibilidad del código, debe tener en cuenta siempre que hace referencia a todas las propiedades de forma explícita, incluso predeterminados propiedades.  
  
 El `Default` modificador se puede usar en este contexto:  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
