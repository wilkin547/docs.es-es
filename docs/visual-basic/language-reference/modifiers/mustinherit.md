---
title: "MustInherit (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "MustInherit"
  - "vb.MustInherit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "clases abstractas, MustInherit (clase)"
  - "clases [Visual Basic], abstractas"
  - "MustInherit (clases), MustInherit (palabra clave)"
  - "MustInherit (palabra clave)"
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# MustInherit (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que una clase sólo se puede utilizar como una clase base y que no se puede crear directamente un objeto a partir de ella.  
  
## Comentarios  
 La finalidad de una *clase base* \(también conocida como *clase abstracta*\) es definir la funcionalidad común a todas las clases que se derivan de ésta.  La clase base evita que las clases derivadas tengan que redefinir los elementos comunes.  En algunos casos, esta funcionalidad común no es lo suficientemente completa para que se pueda utilizar un objeto y cada clase derivada define la funcionalidad que falta.  En estos casos, deseará utilizar el código para crear objetos únicamente a partir de las clases derivadas.  Para ello, puede utilizar `MustInherit` en la clase base.  
  
 Otro utilidad de una clase `MustInherit` es restringir una variable a un conjunto de clases relacionadas.  Puede definir una clase base y derivar todos estas clases relacionadas a partir de ella.  La clase base no necesita proporcionar una funcionalidad común a todas las clases derivadas, aunque se puede utilizar como filtro en la asignación de valores a las variables.  Si el código utilizado declara una variable como clase base, Visual Basic permite asignar únicamente un objeto desde una de las clases derivadas a dicha variable.  
  
 .NET Framework define varias clases `MustInherit`, entre ellas <xref:System.Array>, <xref:System.Enum> y <xref:System.ValueType>.  <xref:System.ValueType> es un ejemplo de una clase base que restringe una variable.  Todos los tipos de valor se derivan de <xref:System.ValueType>.  Si declara una variable como <xref:System.ValueType>, puede asignar sólo tipos de valor a esa variable.  
  
## Reglas  
  
-   **Contexto de la declaración.** Sólo se puede utilizar `MustInherit` en una instrucción `Class`.  
  
-   **Modificadores combinados.** No se puede especificar `MustInherit` junto con `NotInheritable` en la misma declaración.  
  
## Ejemplo  
 En el ejemplo siguiente se ilustra la herencia forzada y el reemplazo forzado.  La clase base `shape` define una variable `acrossLine`.  Las clases `circle` y `square` se derivan de `shape`.  Heredan la definición de `acrossLine`, pero deben definir la función `area` porque ese cálculo es diferente en cada tipo de forma.  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 Puede declarar `shape1` y `shape2` para que sean del tipo `shape`.  Sin embargo, no puede crear un objeto a partir de `shape` porque carece de la funcionalidad de `area` y se ha marcado como `MustInherit`.  
  
 Dado que se declaran como `shape`, las variables `shape1` y `shape2` se restringen a los objetos procedentes de las clases derivadas `circle` y `square`.  Visual Basic no permite asignar ningún otro objeto a estas variables, lo que proporciona un elevado nivel de seguridad de tipos.  
  
## Uso  
 El modificador `MustInherit` se puede utilizar en este contexto:  
  
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## Vea también  
 [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)   
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)