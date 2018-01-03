---
title: "Métodos parciales (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33e34c63988e74be2c22cb7b1358f5e8b04048c6
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="partial-methods-visual-basic"></a>Métodos parciales (Visual Basic)
Los métodos parciales permiten a los desarrolladores insertar lógica personalizada en código. Normalmente, el código es parte de una clase generada por el diseñador. Métodos parciales se definen en una clase parcial que se crea un generador de código y se suelen usar para proporcionar una notificación que algo ha cambiado. Le permiten al programador especificar un comportamiento personalizado en respuesta al cambio.  
  
 El diseñador del generador de código define sólo la firma del método y una o más llamadas al método. Los desarrolladores pueden proporcionar, a continuación, las implementaciones del método si desea personalizar el comportamiento del código generado. Cuando no se proporciona ninguna implementación, se quitan las llamadas al método por el compilador, lo que da lugar ninguna sobrecarga de rendimiento adicional.  
  
## <a name="declaration"></a>Declaración  
 El código generado marca la definición de un método parcial mediante la colocación de la palabra clave `Partial` al principio de la línea de firma.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 La definición debe cumplir las condiciones siguientes:  
  
-   El método debe ser un `Sub`, no un `Function`.  
  
-   El cuerpo del método se debe dejar vacío.  
  
-   El modificador de acceso debe ser `Private`.  
  
## <a name="implementation"></a>Implementación  
 La implementación consiste principalmente en rellenar en el cuerpo del método parcial. La implementación está normalmente en una clase parcial independiente de la definición y se escribe por un desarrollador que desea ampliar el código generado.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 El ejemplo anterior duplica la firma en la declaración exactamente, pero son posibles las variaciones. En concreto, otros modificadores pueden agregarse, como `Overloads` o `Overrides`. Solo un `Overrides` se permite el modificador. Para obtener más información acerca de los modificadores de método, consulte [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Usar  
 Se llama a un método parcial como llamaría a cualquier otro `Sub` procedimiento. Si el método se ha implementado, se evalúan los argumentos y se ejecuta el cuerpo del método. Sin embargo, recuerde que implementa un método parcial es opcional. Si no se implementa el método, una llamada a éste no tiene ningún efecto y no se evalúan las expresiones pasadas como argumentos al método.  
  
## <a name="example"></a>Ejemplo  
 En un archivo denominado Product.Designer.vb, defina un `Product` clase que tiene un `Quantity` propiedad.  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 En un archivo denominado Product.vb, proporcione una implementación para `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 Por último, en el método Main de un proyecto, declare un `Product` instancia y proporcionar un valor inicial para su `Quantity` propiedad.  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 Debe aparecer un cuadro de mensaje que muestra este mensaje:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>Vea también  
 [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Subprocedimientos](./sub-procedures.md)  
 [Parámetros opcionales](./optional-parameters.md)  
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [Generación de código en LINQ to SQL](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [Adición de lógica de negocios utilizando métodos parciales](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
