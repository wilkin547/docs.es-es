---
title: MustInherit (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 5d622c1cff77a45c8de7772af7efbb73586f4400
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)
Especifica que una clase puede usarse únicamente como clase base y que no se puede crear un objeto directamente a partir de él.  
  
## <a name="remarks"></a>Comentarios  
 El propósito de un *clase base* (también conocido como un *clase abstracta*) es definir la funcionalidad común a todas las clases que derivan de él. Esto evita que las clases derivadas tener que volver a definir los elementos comunes. En algunos casos, esta funcionalidad común no es lo suficientemente completa para hacer que un objeto utilizable y cada clase derivada define la funcionalidad que falta. En este caso, desea que el código usado para crear objetos únicamente a partir de las clases derivadas. Usa `MustInherit` en la clase base para exigir esto.  
  
 Otro uso de un `MustInherit` clase consiste en restringir una variable a un conjunto de clases relacionadas. Puede definir una clase base y derivan todas estas clases relacionadas. La clase base no es necesario proporcionar una funcionalidad común a todas las clases derivadas, pero puede actuar como un filtro para asignar valores a variables. Si el código utilizado declara una variable como la clase base, Visual Basic permite asignar solo un objeto de una de las clases derivadas a esa variable.  
  
 .NET Framework define varias `MustInherit` clases, entre ellas <xref:System.Array>, <xref:System.Enum>, y <xref:System.ValueType>. <xref:System.ValueType> es un ejemplo de una clase base que restringe una variable. Todos los tipos de valor se derivan de <xref:System.ValueType>. Si se declara una variable como <xref:System.ValueType>, puede asignar solo los tipos de valor a esa variable.  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de la declaración.** Puede usar `MustInherit` únicamente en un `Class` instrucción.  
  
-   **Modificadores combinados.** No se puede especificar `MustInherit` junto con `NotInheritable` en la misma declaración.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra la herencia forzada y el reemplazo forzado. La clase base `shape` define una variable `acrossLine`. Las clases de `circle` y `square` derivan de `shape`. Heredan la definición de `acrossLine`, pero debe definir la función `area` porque ese cálculo es diferente para cada tipo de forma.  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 Puede declarar `shape1` y `shape2` ser del tipo `shape`. Sin embargo, no se puede crear un objeto de `shape` porque carece de la funcionalidad de la función `area` y está marcado como `MustInherit`.  
  
 Dado que se declaran como `shape`, las variables `shape1` y `shape2` están restringidos a los objetos de las clases derivadas `circle` y `square`. Visual Basic no permite asignar cualquier otro objeto a estas variables, que proporciona un alto nivel de seguridad de tipos.  
  
## <a name="usage"></a>Uso  
 El `MustInherit` modificador se puede usar en este contexto:  
  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)  
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
