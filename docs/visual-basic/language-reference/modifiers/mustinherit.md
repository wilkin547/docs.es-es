---
title: MustInherit
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
ms.openlocfilehash: 6502da947ae331a26e66d8ce2dbcda46e4172a6e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867954"
---
# <a name="mustinherit-visual-basic"></a>MustInherit (Visual Basic)

Especifica que una clase se puede usar solo como una clase base y que no se puede crear un objeto directamente a partir de ella.  
  
## <a name="remarks"></a>Comentarios  

 El propósito de una *clase base* (también conocida como *clase abstracta*) es definir la funcionalidad común a todas las clases derivadas de ella. Esto evita que las clases derivadas tengan que volver a definir los elementos comunes. En algunos casos, esta funcionalidad común no es suficiente para crear un objeto utilizable y cada clase derivada define la funcionalidad que falta. En tal caso, desea que el código utilizado solo cree objetos a partir de las clases derivadas. Utilice `MustInherit` en la clase base para aplicar este.  
  
 Otro uso de una `MustInherit` clase es restringir una variable a un conjunto de clases relacionadas. Puede definir una clase base y derivar todas estas clases relacionadas de ella. No es necesario que la clase base proporcione ninguna funcionalidad común a todas las clases derivadas, pero puede servir como filtro para asignar valores a variables. Si el código utilizado declara una variable como la clase base, Visual Basic le permite asignar solo un objeto de una de las clases derivadas a esa variable.  
  
 El .NET Framework define varias `MustInherit` clases, entre ellas <xref:System.Array> , <xref:System.Enum> y <xref:System.ValueType> . <xref:System.ValueType> es un ejemplo de una clase base que restringe una variable. Todos los tipos de valor se derivan de <xref:System.ValueType> . Si declara una variable como <xref:System.ValueType> , solo podrá asignar tipos de valor a esa variable.  
  
## <a name="rules"></a>Reglas  
  
- **Contexto de declaración.** Solo se puede usar `MustInherit` en una `Class` instrucción.  
  
- **Modificadores combinados.** No se puede especificar `MustInherit` junto con `NotInheritable` en la misma declaración.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra la herencia forzada y el reemplazo forzado. La clase base `shape` define una variable `acrossLine` . Las clases `circle` y `square` derivan de `shape` . Heredan la definición de `acrossLine` , pero deben definir la función `area` porque ese cálculo es diferente para cada tipo de forma.  
  
 [!code-vb[VbVbalrKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#2)]  
  
 Puede declarar `shape1` y `shape2` para que sean de tipo `shape` . Sin embargo, no se puede crear un objeto desde `shape` porque carece de la funcionalidad de la función `area` y está marcado como `MustInherit` .  
  
 Dado que se declaran como `shape` , las variables `shape1` y `shape2` están restringidas a los objetos de las clases derivadas `circle` y `square` . Visual Basic no permite asignar ningún otro objeto a estas variables, lo que proporciona un alto nivel de seguridad de tipos.  
  
## <a name="usage"></a>Uso  

 El `MustInherit` modificador se puede usar en este contexto:  
  
 [Instrucción Class](../statements/class-statement.md)  
  
## <a name="see-also"></a>Consulte también

- [Inherits Statement](../statements/inherits-statement.md)
- [NotInheritable](notinheritable.md)
- [Palabras clave](../keywords/index.md)
- [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
