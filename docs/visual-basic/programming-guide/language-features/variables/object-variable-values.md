---
title: Valores de las variables de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: a5152ad0e5e5ac876783c2b191ee13e845593df8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652121"
---
# <a name="object-variable-values-visual-basic"></a>Valores de las variables de objeto (Visual Basic)
Una variable de la [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) puede hacer referencia a datos de cualquier tipo. El valor que se almacena en un `Object` variable se mantiene en otra ubicación en memoria, mientras que la propia variable contiene un puntero a los datos.  
  
## <a name="object-classifier-functions"></a>Funciones de clasificador de objetos  
 Visual Basic proporciona funciones que devuelven información acerca de lo que un `Object` variable hace referencia a, como se muestra en la tabla siguiente.  
  
|Función|Devuelve True si la variable de objeto hace referencia a|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Una matriz de valores, en lugar de un solo valor|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|A [tipo de datos Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) valor o una cadena que se puede interpretar como un valor de fecha y hora|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Un objeto de tipo <xref:System.DBNull>, que representa los datos que faltan o que no existe|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Un objeto de excepción, que se deriva de <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Nada](../../../../visual-basic/language-reference/nothing.md), es decir, no hay ningún objeto está asignado actualmente a la variable|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Un número o una cadena que se puede interpretar como un número|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Un tipo de referencia (por ejemplo, una cadena, matriz, delegado o tipo de clase)|  
  
 Puede utilizar estas funciones para impedir que se envíe un valor no válido a una operación o un procedimiento.  
  
## <a name="typeof-operator"></a>Operador TypeOf  
 También puede usar el [del operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) para determinar si una variable de objeto hace referencia actualmente a un tipo de datos específico. El `TypeOf`... `Is` expresión se evalúa como `True` si el tipo de tiempo de ejecución del operando se deriva de o implementa el tipo especificado.  
  
 En el ejemplo siguiente se usa `TypeOf` en variables de objeto que hacen referencia a tipos de valor y de referencia.  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 En el ejemplo anterior, se escribe las siguientes líneas a la **depurar** ventana:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 La variable de objeto `num` hace referencia a datos de tipo `Integer`, y `frm` hace referencia a un objeto de clase <xref:System.Windows.Forms.Form>.  
  
## <a name="object-arrays"></a>Matrices de objetos  
 Puede declarar y utilizar una matriz de `Object` variables. Esto es útil si necesita controlar una variedad de tipos de datos y las clases de objeto. Todos los elementos de matriz deben tener los mismos datos declarados de tipo. Este tipo de datos que se declara `Object` le permite almacenar objetos e instancias junto con otros tipos de datos de la matriz de clase.  
  
## <a name="see-also"></a>Vea también  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Hacer referencia a la instancia actual de un objeto](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)  
 [Determinar el tipo al que hace referencia una variable de objeto](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)  
 [Determinar si dos objetos están relacionados](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Determinar si dos objetos son idénticos](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
