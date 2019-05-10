---
title: Promoción de tipos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: 02d53770186f7600b190231dc73938ff1589cef6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610355"
---
# <a name="type-promotion-visual-basic"></a>Promoción de tipos (Visual Basic)
Cuando se declara un elemento de programación en un módulo, Visual Basic promueve su ámbito al espacio de nombres que contiene el módulo. Esto se conoce como *promoción de tipos*.  
  
 El ejemplo siguiente muestra un esquema de definición de un módulo y dos miembros de ese módulo.  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 Dentro de `projModule`, programación los elementos declarados en el nivel de módulo se promueven a `projNamespace`. En el ejemplo anterior, `basicEnum` y `innerClass` se promocionan, pero `numberSub` es no, porque no está declarado en el nivel de módulo.  
  
## <a name="effect-of-type-promotion"></a>Efecto de promoción de tipos  
 El efecto de promoción de tipos es que una cadena de calificación no necesita incluir el nombre del módulo. El ejemplo siguiente hace dos llamadas al procedimiento en el ejemplo anterior.  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 En el ejemplo anterior, la primera llamada usa cadenas de calificación completa. Sin embargo, esto no es necesario debido a la promoción de tipos. La segunda llamada también tiene acceso a los miembros del módulo sin incluir `projModule` en las cadenas de calificación.  
  
## <a name="defeat-of-type-promotion"></a>Rechazo de promoción de tipos  
 Si el espacio de nombres ya tiene un miembro con el mismo nombre como miembro de un módulo, la promoción de tipos se rechaza para ese miembro del módulo. El ejemplo siguiente muestra un esquema de definición de una enumeración y un módulo en el mismo espacio de nombres.  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 En el ejemplo anterior, Visual Basic no se puede promover la clase `abc` a `thisNameSpace` porque ya hay una enumeración con el mismo nombre en el nivel de espacio de nombres. Para tener acceso a `abcSub`, debe usar la cadena de calificación completa `thisNamespace.thisModule.abc.abcSub`. Sin embargo, la clase `xyz` todavía se promueve, y puede tener acceso a `xyzSub` con la cadena de calificación más corta `thisNamespace.xyz.xyzSub`.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Rechazo de promoción de tipos para tipos parciales  
 Si una clase o estructura dentro de un módulo usa la [parcial](../../../../visual-basic/language-reference/modifiers/partial.md) palabra clave, se rechaza automáticamente para esa clase o estructura, la promoción de tipos si el espacio de nombres tiene un miembro con el mismo nombre. Otros elementos en el módulo siguen siendo aptos para la promoción de tipos.  
  
 **Consecuencias.** Rechazo de promoción de tipo de una definición parcial de puede producir resultados inesperados e incluso errores del compilador. El ejemplo siguiente muestra el esqueletos definiciones parciales de una clase, una de las cuales está dentro de un módulo.  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 En el ejemplo anterior, el desarrollador podría esperar que el compilador para combinar las dos definiciones parciales de `sampleClass`. Sin embargo, el compilador no considera la promoción para la definición parcial dentro de `sampleModule`. Como resultado, intenta compilar dos clases independientes y distintas, ambos denominados `sampleClass` pero con las rutas de acceso de calificación diferentes.  
  
 El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.  
  
## <a name="recommendations"></a>Recomendaciones  
 Las recomendaciones siguientes representan buena práctica de programación.  
  
- **Nombres únicos.** Cuando tenga control total sobre la nomenclatura de elementos de programación, siempre es una buena idea usar nombres únicos en todas partes. Nombres idénticos requieran la calificación adicional y pueden hacer que el código sea más difícil de leer. También pueden conducir a errores sutiles y resultados imprevistos.  
  
- **Usar el nombre completo.** Cuando se trabaja con módulos y otros elementos en el mismo espacio de nombres, el enfoque más seguro es utilizar siempre la calificación completa para todos los elementos de programación. Si la promoción de tipos se rechaza para un miembro del módulo y no calificar totalmente ese miembro, podría tener acceso a un elemento de programación diferentes sin darse cuenta.  
  
## <a name="see-also"></a>Vea también

- [Module (instrucción)](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Namespace (instrucción)](../../../../visual-basic/language-reference/statements/namespace-statement.md)
- [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)
- [Ámbito en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Cómo: Controlar el ámbito de una Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [Referencias a elementos declarados](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
