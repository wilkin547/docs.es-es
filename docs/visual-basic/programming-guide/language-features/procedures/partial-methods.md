---
title: "M&#233;todos parciales (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.PartialMethod"
  - "PartialMethod"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "lógica personalizada en el código [Visual Basic]"
  - "insertar lógica personalizada en el código"
  - "métodos [Visual Basic], métodos parciales"
  - "métodos parciales [Visual Basic]"
  - "partial, métodos [Visual Basic]"
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# M&#233;todos parciales (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Los métodos parciales permiten a los programadores insertar la lógica personalizada en el código.  Normalmente, el código forma parte de una clase generada por el diseñador.  Los métodos parciales se definen en una clase parcial que crea un generador de código y se suelen usar para notificar que se ha cambiado algo.  Permiten al programador especificar el comportamiento personalizado en respuesta al cambio.  
  
 El diseñador del generador de código define sólo la firma de método y una o más llamadas al mismo.  Después, los programadores pueden proporcionar las implementaciones del método si desean personalizar el comportamiento del código generado.  Cuando no se proporciona ninguna implementación, el compilador quita las llamadas al método produciéndose una sobrecarga de rendimiento adicional.  
  
## Declaración  
 El código generado marca la definición de un método parcial colocando la palabra clave `Partial` al principio de la línea de firma.  
  
```vb#  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 La definición debe cumplir las condiciones siguientes:  
  
-   El método debe ser `Sub`, no `Function`.  
  
-   El cuerpo del método debe quedar vacío.  
  
-   El modificador de acceso debe ser `Private`.  
  
## Implementación  
 La implementación está formada principalmente por el rellenado del cuerpo del método parcial.  Normalmente, la implementación está en una clase parcial independiente de la definición y la escribe un programador que desea extender el código generado.  
  
```vb#  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 El ejemplo anterior duplica la firma en la declaración exactamente, pero son posibles las variaciones.  En particular, se pueden agregar otros modificadores, como `Overloads` u `Overrides`.  Se permite sólo un modificador `Overrides`.  Para obtener más información sobre modificadores de métodos, vea [Sub \(Instrucción\)](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## Utilice  
 Llame a un método parcial como llamaría a cualquier otro procedimiento `Sub`.  Si se ha implementado el método, se evalúan los argumentos y se ejecuta el cuerpo del método.  Sin embargo, recuerde que implementar un método parcial es opcional.  Si no se implementa el método, una llamada a éste no tiene ningún efecto y no se evalúan las expresiones pasadas como argumentos al método.  
  
## Ejemplo  
 En un archivo denominado Product.Designer.vb, defina una clase `Product` que tiene una propiedad `Quantity`.  
  
 [!code-vb[VbVbalrPartialMeths#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 En un archivo denominado Product.vb, proporcione una implementación para `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 Finalmente, en el método Main de un proyecto, declare una instancia de `Product` y proporcione un valor inicial para su propiedad `Quantity`.  
  
 [!code-vb[VbVbalrPartialMeths#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 Debe aparecer un cuadro de mensaje con este mensaje:  
  
 `Quantity was changed to 100`  
  
## Vea también  
 [Sub \(Instrucción\)](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Parámetros opcionales](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [Generación de código en LINQ to SQL](../Topic/Code%20Generation%20in%20LINQ%20to%20SQL.md)   
 [Agregar lógica empresarial utilizando métodos Partial](../Topic/Adding%20Business%20Logic%20By%20Using%20Partial%20Methods.md)