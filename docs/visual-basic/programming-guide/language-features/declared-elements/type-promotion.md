---
title: "Promoción de tipos (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3a55c023afe7afe96f862f0b3cbbdb03a15b902
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="type-promotion-visual-basic"></a>Promoción de tipos (Visual Basic)
Cuando se declara un elemento de programación en un módulo, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] promueve su ámbito al espacio de nombres que contiene el módulo. Esto se conoce como *promoción de tipo*.  
  
 En el ejemplo siguiente se muestra un esquema de definición de un módulo y dos miembros de ese módulo.  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 Dentro de `projModule`, programación elementos declarados en el nivel de módulo se promueven a `projNamespace`. En el ejemplo anterior, `basicEnum` y `innerClass` se promocionan, pero `numberSub` no, es porque no se ha declarado en el nivel de módulo.  
  
## <a name="effect-of-type-promotion"></a>Efecto de promoción de tipos  
 El efecto de la promoción de tipos es que una cadena de calificación no necesita incluir el nombre del módulo. En el ejemplo siguiente se realiza dos llamadas al procedimiento en el ejemplo anterior.  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 En el ejemplo anterior, la primera llamada usa cadenas de calificación completas. Sin embargo, esto no es necesario debido a la promoción de tipos. La segunda llamada también tiene acceso a los miembros del módulo sin incluir `projModule` en las cadenas de calificación.  
  
## <a name="defeat-of-type-promotion"></a>Rechazo de promoción de tipos  
 Si el espacio de nombres ya tiene un miembro con el mismo nombre que un miembro del módulo, la promoción de tipos se rechaza para ese miembro del módulo. En el ejemplo siguiente se muestra un esquema de definición de una enumeración y un módulo dentro del mismo espacio de nombres.  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 En el ejemplo anterior, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] no se puede promover la clase `abc` a `thisNameSpace` porque ya hay una enumeración con el mismo nombre en el nivel de espacio de nombres. Para tener acceso a `abcSub`, debe utilizar la cadena de calificación completa `thisNamespace.thisModule.abc.abcSub`. Sin embargo, la clase `xyz` todavía se promueve, y puede tener acceso a `xyzSub` con la cadena de calificación más corta `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Rechazo de promoción de tipos para tipos parciales.  
 Si una clase o estructura dentro de un módulo usa la [parcial](../../../../visual-basic/language-reference/modifiers/partial.md) palabra clave, se rechaza automáticamente para esa clase o estructura, la promoción de tipos si el espacio de nombres tiene un miembro con el mismo nombre o no. Otros elementos en el módulo son aún aptos para la promoción de tipos.  
  
 **Consecuencias.** Rechazo de promoción de tipos de una definición parcial puede producir resultados inesperados e incluso errores del compilador. En el ejemplo siguiente se muestra el esqueletos definiciones parciales de una clase, una de las cuales está dentro de un módulo.  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 En el ejemplo anterior, el desarrollador podría esperar que el compilador para combinar las dos definiciones parciales de `sampleClass`. Sin embargo, el compilador no tiene en cuenta para la definición parcial dentro de la promoción `sampleModule`. Como resultado, intenta compilar dos clases independientes y distintas, ambos denominados `sampleClass` pero con las rutas de acceso de calificación diferentes.  
  
 El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.  
  
## <a name="recommendations"></a>Recomendaciones  
 Las recomendaciones siguientes representan buena práctica de programación.  
  
-   **Nombres únicos.** Si tiene control total sobre la nomenclatura de los elementos de programación, siempre es una buena idea usar nombres únicos en todas partes. Nombres idénticos requieren calificación adicional y pueden hacer que el código sea más difícil de leer. También puede llevar a errores imperceptibles y resultados inesperados.  
  
-   **Usar el nombre completo.** Cuando se trabaja con módulos y otros elementos en el mismo espacio de nombres, el enfoque más seguro es utilizar siempre la calificación completa para todos los elementos de programación. Si la promoción de tipos se rechaza para un miembro del módulo y no completos a ese miembro, sin darse cuenta podría tener acceso a un elemento de programación diferente.  
  
## <a name="see-also"></a>Vea también  
 [Module (instrucción)](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Namespace (instrucción)](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Controlar el ámbito de una variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
