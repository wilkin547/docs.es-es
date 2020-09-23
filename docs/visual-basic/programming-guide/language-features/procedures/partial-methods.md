---
title: Métodos Partial
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
ms.openlocfilehash: 0e7c1315df50e83c919270f76405e80862bdd03b
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071266"
---
# <a name="partial-methods-visual-basic"></a>Métodos parciales (Visual Basic)

Los métodos parciales permiten a los desarrolladores insertar lógica personalizada en el código. Normalmente, el código forma parte de una clase generada por el diseñador. Los métodos parciales se definen en una clase parcial que se crea mediante un generador de código y se suelen usar para proporcionar una notificación de que se ha cambiado algo. Permiten al desarrollador especificar el comportamiento personalizado en respuesta al cambio.  
  
 El diseñador del generador de código solo define la firma del método y una o varias llamadas al método. Después, los desarrolladores pueden proporcionar implementaciones para el método si quieren personalizar el comportamiento del código generado. Cuando no se proporciona ninguna implementación, el compilador quita las llamadas al método, lo que da lugar a una sobrecarga de rendimiento adicional.  
  
## <a name="declaration"></a>Declaración  

 El código generado marca la definición de un método parcial colocando la palabra clave `Partial` al principio de la línea de firma.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 La definición debe cumplir las siguientes condiciones:  
  
- El método debe ser un `Sub` , no un `Function` .  
  
- El cuerpo del método debe dejarse vacío.  
  
- El modificador de acceso debe ser `Private` .  
  
## <a name="implementation"></a>Implementación  

 La implementación consiste principalmente en rellenar el cuerpo del método parcial. La implementación está normalmente en una clase parcial independiente de la definición y está escrita por un desarrollador que desea extender el código generado.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 En el ejemplo anterior se duplica exactamente la firma en la declaración, pero son posibles las variaciones. En concreto, se pueden agregar otros modificadores, como `Overloads` o `Overrides` . Solo `Overrides` se permite un modificador. Para obtener más información sobre los modificadores de método, vea [Sub Statement](../../../language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Uso  

 Se llama a un método parcial como se llamaría a cualquier otro `Sub` procedimiento. Si se ha implementado el método, se evalúan los argumentos y se ejecuta el cuerpo del método. Sin embargo, recuerde que la implementación de un método parcial es opcional. Si no se implementa el método, no se evalúa ninguna llamada a él y no se evalúan las expresiones que se pasan como argumentos al método.  
  
## <a name="example"></a>Ejemplo  

 En un archivo denominado product. Designer. VB, defina una `Product` clase que tenga una `Quantity` propiedad.  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 En un archivo denominado product. VB, proporcione una implementación para `QuantityChanged` .  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 Por último, en el método Main de un proyecto, declare una `Product` instancia de y proporcione un valor inicial para su `Quantity` propiedad.  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 Debería aparecer un cuadro de mensaje que muestra este mensaje:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>Vea también

- [Instrucción Sub](../../../language-reference/statements/sub-statement.md)
- [Procedimientos Sub](./sub-procedures.md)
- [Parámetros opcionales](./optional-parameters.md)
- [Partial](../../../language-reference/modifiers/partial.md)
- [Generación de código en LINQ to SQL](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [Agregar lógica de negocios utilizando métodos parciales](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
