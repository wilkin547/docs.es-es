---
title: Promoción de tipos
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
ms.openlocfilehash: 1e284b99a36cdf0f62aee2c45fd9f3bf544d1d81
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410713"
---
# <a name="type-promotion-visual-basic"></a>Promoción de tipos (Visual Basic)
Cuando se declara un elemento de programación en un módulo, Visual Basic promociona su ámbito al espacio de nombres que contiene el módulo. Esto se conoce como *promoción de tipos*.  
  
 En el ejemplo siguiente se muestra una definición de esqueleto de un módulo y dos miembros de ese módulo.  
  
 [!code-vb[VbVbalrDeclaredElements#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#1)]  
  
 Dentro de `projModule` , los elementos de programación declarados en el nivel de módulo se promueven a `projNamespace` . En el ejemplo anterior, `basicEnum` `innerClass` se promocionan y, pero `numberSub` no es, porque no se ha declarado en el nivel de módulo.  
  
## <a name="effect-of-type-promotion"></a>Efecto de la promoción de tipos  
 El efecto de la promoción de tipos es que una cadena de calificación no necesita incluir el nombre del módulo. En el ejemplo siguiente se realizan dos llamadas al procedimiento en el ejemplo anterior.  
  
 [!code-vb[VbVbalrDeclaredElements#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#2)]  
  
 En el ejemplo anterior, la primera llamada utiliza cadenas de calificación completas. Sin embargo, esto no es necesario debido a la promoción de tipos. La segunda llamada también tiene acceso a los miembros del módulo sin incluir `projModule` en las cadenas de calificación.  
  
## <a name="defeat-of-type-promotion"></a>Derrota de promoción de tipos  
 Si el espacio de nombres ya tiene un miembro con el mismo nombre que un miembro del módulo, la promoción de tipos es derrota para ese miembro del módulo. En el ejemplo siguiente se muestra una definición de esqueleto de una enumeración y un módulo dentro del mismo espacio de nombres.  
  
 [!code-vb[VbVbalrDeclaredElements#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#3)]  
  
 En el ejemplo anterior, Visual Basic no puede promover la clase `abc` a `thisNameSpace` porque ya hay una enumeración con el mismo nombre en el nivel de espacio de nombres. Para tener acceso a `abcSub` , debe usar la cadena de calificación completa `thisNamespace.thisModule.abc.abcSub` . Sin embargo, `xyz` se sigue promoviendo la clase y se puede tener acceso a `xyzSub` la cadena de calificación más corta `thisNamespace.xyz.xyzSub` .  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>Derrotar la promoción de tipos para tipos parciales  
 Si una clase o estructura dentro de un módulo utiliza la palabra clave [partial](../../../language-reference/modifiers/partial.md) , la promoción de tipos se rechaza automáticamente para esa clase o estructura, tanto si el espacio de nombres tiene un miembro con el mismo nombre como si no. Otros elementos del módulo siguen siendo válidos para la promoción de tipos.  
  
 **Derivada.** La anulación de la promoción de tipos de una definición parcial puede producir resultados inesperados e incluso errores del compilador. En el ejemplo siguiente se muestran definiciones parciales de esqueleto de una clase, una de las cuales está dentro de un módulo.  
  
 [!code-vb[VbVbalrDeclaredElements#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDeclaredElements/VB/Class1.vb#4)]  
  
 En el ejemplo anterior, el desarrollador podría esperar que el compilador combine las dos definiciones parciales de `sampleClass` . Sin embargo, el compilador no considera la promoción de la definición parcial dentro de `sampleModule` . Como resultado, intenta compilar dos clases independientes y distintas, con el mismo nombre `sampleClass` pero con diferentes rutas de acceso de calificación.  
  
 El compilador solo combina las definiciones parciales cuando sus rutas de acceso completas son idénticas.  
  
## <a name="recommendations"></a>Recomendaciones  
 Las siguientes recomendaciones representan una buena práctica de programación.  
  
- **Nombres únicos.** Cuando tenga control total sobre la nomenclatura de los elementos de programación, siempre es una buena idea usar nombres únicos en todas partes. Los nombres idénticos requieren una calificación adicional y pueden dificultar la lectura del código. También pueden provocar errores sutiles y resultados inesperados.  
  
- **Calificación completa.** Cuando se trabaja con módulos y otros elementos en el mismo espacio de nombres, el enfoque más seguro es usar siempre la calificación completa de todos los elementos de programación. Si la promoción de tipos es derrota para un miembro del módulo y no se certifica totalmente ese miembro, se podría tener acceso accidentalmente a un elemento de programación diferente.  
  
## <a name="see-also"></a>Consulte también

- [Module (Instrucción)](../../../language-reference/statements/module-statement.md)
- [Namespace (Instrucción)](../../../language-reference/statements/namespace-statement.md)
- [Partial](../../../language-reference/modifiers/partial.md)
- [Ámbito en Visual Basic](scope.md)
- [Procedimiento para controlar el ámbito de una variable](how-to-control-the-scope-of-a-variable.md)
- [References to Declared Elements](references-to-declared-elements.md)
