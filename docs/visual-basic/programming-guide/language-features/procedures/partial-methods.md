---
title: Métodos parciales (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 765a667f18340c53909c3ff1e9fcc5f2ffc0f9bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791942"
---
# <a name="partial-methods-visual-basic"></a>Métodos parciales (Visual Basic)
Los métodos parciales permiten a los desarrolladores insertar lógica personalizada en código. Normalmente, el código es parte de una clase generada por el diseñador. Los métodos parciales se definen en una clase parcial que se crea un generador de código y se suelen usar para proporcionar una notificación que algo ha cambiado. Le permiten al programador especificar un comportamiento personalizado en respuesta al cambio.  
  
 El diseñador del generador de código define solo la firma del método y una o más llamadas al método. Los desarrolladores, a continuación, pueden proporcionar las implementaciones del método si desean personalizar el comportamiento del código generado. Cuando no se proporciona ninguna implementación, se quitan las llamadas al método por el compilador, lo que resulta en ninguna sobrecarga de rendimiento adicionales.  
  
## <a name="declaration"></a>Declaración  
 El código generado marca la definición de un método parcial colocando la palabra clave `Partial` al principio de la línea de firma.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 La definición debe cumplir las condiciones siguientes:  
  
- El método debe ser un `Sub`, no un `Function`.  
  
- El cuerpo del método debe dejarse vacío.  
  
- El modificador de acceso debe ser `Private`.  
  
## <a name="implementation"></a>Implementación  
 La implementación consiste principalmente en rellenar en el cuerpo del método parcial. La implementación está normalmente en una clase parcial independiente de la definición y escrita por un desarrollador que desea ampliar el código generado.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 En el ejemplo anterior se duplica la firma en la declaración exactamente, pero son posibles variaciones. En concreto, otros modificadores pueden agregarse, como `Overloads` o `Overrides`. Solo un `Overrides` modificador está permitido. Para obtener más información acerca de los modificadores de método, consulte [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Usar  
 Llamar a un método parcial como llamaría a cualquier otro `Sub` procedimiento. Si se ha implementado el método, los argumentos se evalúan y se ejecuta el cuerpo del método. Sin embargo, recuerde que la implementación de un método parcial es opcional. Si no se implementa el método, una llamada a la no tiene ningún efecto y no se evalúan las expresiones pasadas como argumentos al método.  
  
## <a name="example"></a>Ejemplo  
 En un archivo denominado Product.Designer.vb, defina un `Product` clase que tiene un `Quantity` propiedad.  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 En un archivo denominado Product.vb, proporcione una implementación para `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 Por último, en el método Main de un proyecto, declare un `Product` de instancia y proporcionar un valor inicial para su `Quantity` propiedad.  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 Debe aparecer un cuadro de mensaje que muestra este mensaje:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>Vea también

- [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Subprocedimientos](./sub-procedures.md)
- [Parámetros opcionales](./optional-parameters.md)
- [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)
- [Generación de código en LINQ to SQL](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [Adición de lógica de negocios utilizando métodos parciales](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
