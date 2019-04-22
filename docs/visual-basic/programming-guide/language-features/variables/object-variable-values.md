---
title: Valores de las variables de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: c17c5f85952596f0a080ca473e8f792740e66b8f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840398"
---
# <a name="object-variable-values-visual-basic"></a>Valores de las variables de objeto (Visual Basic)
Una variable de la [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) puede hacer referencia a datos de cualquier tipo. El valor que se almacena en un `Object` variable se mantiene en otro lugar en la memoria, mientras que la propia variable contiene un puntero a los datos.  
  
## <a name="object-classifier-functions"></a>Funciones del objeto clasificador  
 Visual Basic proporciona funciones que devuelven información acerca de lo que un `Object` variable hace referencia a, tal como se muestra en la tabla siguiente.  
  
|Función|Devuelve True si la variable de objeto hace referencia a|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Una matriz de valores, en lugar de un solo valor|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Un [tipo de datos Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) valor o una cadena que se puede interpretar como un valor de fecha y hora|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Un objeto de tipo <xref:System.DBNull>, que representa los datos que faltan o que no existentes|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Un objeto de excepción que se deriva de <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[No hay nada](../../../../visual-basic/language-reference/nothing.md), es decir, no hay ningún objeto está asignado actualmente a la variable|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Un número o una cadena que se puede interpretar como un número|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Un tipo de referencia (por ejemplo, una cadena, matriz, delegado o tipo de clase)|  
  
 Puede usar estas funciones para evitar el envío de un valor no válido a una operación o un procedimiento.  
  
## <a name="typeof-operator"></a>Operador TypeOf  
 También puede usar el [operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) para determinar si una variable de objeto hace referencia actualmente a un tipo de datos específico. El `TypeOf`... `Is` expresión se evalúa como `True` si el tipo de tiempo de ejecución del operando se deriva de o implementa el tipo especificado.  
  
 En el ejemplo siguiente se usa `TypeOf` en variables de objeto que hace referencia a tipos de valor y de referencia.  
  
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
  
 El ejemplo anterior escribe las líneas siguientes a la **depurar** ventana:  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 La variable de objeto `num` hace referencia a datos de tipo `Integer`, y `frm` hace referencia a un objeto de clase <xref:System.Windows.Forms.Form>.  
  
## <a name="object-arrays"></a>Matrices de objetos  
 Puede declarar y usar una matriz de `Object` variables. Esto es útil cuando deba controlar una variedad de tipos de datos y las clases de objeto. Todos los elementos de matriz deben tener los mismos datos declarados de tipo. Este tipo de datos como se declara `Object` le permite almacenar objetos e instancias junto con otros tipos de datos de la matriz de clase.  
  
## <a name="see-also"></a>Vea también

- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Cómo: Hacer referencia a la instancia actual de un objeto](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Cómo: Determinar qué tipo de una Variable de objeto hace referencia a](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [Cómo: Determinar si dos objetos están relacionados](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Cómo: Determinar si dos objetos son idénticos](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
