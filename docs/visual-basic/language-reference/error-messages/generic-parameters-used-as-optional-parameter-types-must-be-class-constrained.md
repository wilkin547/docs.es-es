---
title: "Los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords: BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a13ea66f12e54db4e585577e20e1f5396669f1a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>Los parámetros genéricos utilizados como tipos de parámetros opcionales deben tener restricción de clase
Se declara un procedimiento con un parámetro opcional que utiliza un parámetro de tipo que no está restringido a ser un tipo de referencia.  
  
 Siempre debe proporcionar un valor predeterminado para cada parámetro opcional. Si el parámetro es de un tipo de referencia, el valor opcional debe ser `Nothing`, que es un valor válido para cualquier tipo de referencia. Sin embargo, si el parámetro es de un tipo de valor, ese tipo debe ser un tipo de datos básico predefinido por Visual Basic. Esto es porque un tipo de valor compuesto, como una estructura definida por el usuario, no tiene ningún valor predeterminado válido.  
  
 Cuando se usa un parámetro de tipo para un parámetro opcional, debe garantizar que es de un tipo de referencia para evitar la posibilidad de un tipo de valor no tiene ningún valor predeterminado válido. Esto significa que debe restringir el parámetro de tipo con el `Class` palabra clave o con el nombre de una clase específica.  
  
 **Id. de error:** BC32124  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Restringir el parámetro de tipo para aceptar sólo un tipo de referencia o no lo use para el parámetro opcional.  
  
## <a name="see-also"></a>Vea también  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Nothing](../../../visual-basic/language-reference/nothing.md)
