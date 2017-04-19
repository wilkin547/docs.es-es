---
title: "Tipo de promoción (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, scope
- visibility, declared elements
- Partial keyword, unexpected results with type promotion
- scope, declared elements
- scope, Visual Basic
- type promotion
- declared elements, visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d732e765fc28eaedc0deab477dbf9955a40e97c9
ms.lasthandoff: 03/13/2017

---
# <a name="type-promotion-visual-basic"></a>Promoción de tipos (Visual Basic)
Cuando se declara un elemento de programación en un módulo, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] promueve su ámbito al espacio de nombres que contiene el módulo. Esto se conoce como *promoción de tipo*.  
  
 En el ejemplo siguiente se muestra un esquema de definición de un módulo y dos miembros de ese módulo.  
  
 [!code-vb[1 VbVbalrDeclaredElements](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 Dentro de `projModule`, programación elementos declarados en el nivel de módulo se promueven a `projNamespace`. En el ejemplo anterior, `basicEnum` y `innerClass` se promocionan, pero `numberSub` es no, porque no se ha declarado en el nivel de módulo.  
  
## <a name="effect-of-type-promotion"></a>Efecto de promoción de tipos  
 El efecto de promoción de tipos es que una cadena de calificación no necesita incluir el nombre del módulo. En el ejemplo siguiente se hace dos llamadas al procedimiento en el ejemplo anterior.  
  
 [!code-vb[VbVbalrDeclaredElements&#2;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 En el ejemplo anterior, la primera llamada utiliza las cadenas de calificación completas. Sin embargo, esto no es necesario debido a la promoción de tipos. La segunda llamada también tiene acceso a los miembros del módulo sin incluir `projModule` en las cadenas de calificación.  
  
## <a name="defeat-of-type-promotion"></a>Rechazo de promoción de tipos  
 Si el espacio de nombres ya tiene un miembro con el mismo nombre que un miembro de módulo, la promoción de tipos se rechaza para ese miembro del módulo. En el ejemplo siguiente se muestra un esquema de definición de una enumeración y un módulo dentro del mismo espacio de nombres.  
  
 [!code-vb[VbVbalrDeclaredElements&3;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 En el ejemplo anterior, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] no se puede promover la clase `abc` a `thisNameSpace` porque ya hay una enumeración con el mismo nombre en el nivel de espacio de nombres. Para tener acceso a `abcSub`, debe utilizar la cadena de calificación completa `thisNamespace.thisModule.abc.abcSub`. Sin embargo, la clase `xyz` todavía se promueve, y puede tener acceso a `xyzSub` con la cadena de calificación más corta `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Rechazo de promoción de tipos para tipos parciales  
 Si una clase o estructura dentro de un módulo utiliza el [parcial](../../../../visual-basic/language-reference/modifiers/partial.md) (palabra clave), la promoción de tipos se rechaza automáticamente para esa clase o estructura, si el espacio de nombres tiene un miembro con el mismo nombre o no. Otros elementos en el módulo están aún aptos para la promoción de tipos.  
  
 **Consecuencias.** Rechazo de promoción de tipos de una definición parcial puede provocar resultados inesperados e incluso errores del compilador. El ejemplo siguiente muestra definiciones esquemáticas parciales de una clase, una de las cuales está dentro de un módulo.  
  
 [!code-vb[VbVbalrDeclaredElements Nº&4;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 En el ejemplo anterior, el desarrollador podría esperar que el compilador para combinar las dos definiciones parciales de `sampleClass`. Sin embargo, el compilador no considera la promoción para la definición parcial dentro de `sampleModule`. Como resultado, intenta compilar dos clases independientes y distintas, ambos denominados `sampleClass` pero con rutas de acceso de calificación diferentes.  
  
 El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.  
  
## <a name="recommendations"></a>Recomendaciones  
 Las recomendaciones siguientes representan buena práctica de programación.  
  
-   **Nombres únicos.** Cuando tenga control total sobre la nomenclatura de los elementos de programación, siempre es una buena idea utilizar nombres únicos en todas partes. Nombres idénticos requieren calificación adicional y pueden hacer que su código sea más difícil de leer. También pueden llevar a errores imperceptibles y resultados inesperados.  
  
-   **Calificación completa.** Cuando se trabaja con módulos y otros elementos en el mismo espacio de nombres, el enfoque más seguro es utilizar siempre una calificación completa para todos los elementos de programación. Si la promoción de tipos se rechaza para un miembro del módulo y no califica a ese miembro completamente, sin darse cuenta podría tener acceso a un elemento de programación diferente.  
  
## <a name="see-also"></a>Vea también  
 [Module (instrucción)](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Instrucción Namespace](../../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Parcial](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Cómo: controlar el ámbito de una Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)   
 [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
