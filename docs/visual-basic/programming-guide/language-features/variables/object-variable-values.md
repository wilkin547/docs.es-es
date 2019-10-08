---
title: Valores de las variables de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: 728f097b3c084e5292cb2d2bf5a0c1d20bdad922
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004587"
---
# <a name="object-variable-values-visual-basic"></a>Valores de las variables de objeto (Visual Basic)
Una variable del [tipo de datos Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) puede hacer referencia a datos de cualquier tipo. El valor que se almacena en una variable `Object` se mantiene en cualquier parte de la memoria, mientras que la propia variable contiene un puntero a los datos.  
  
## <a name="object-classifier-functions"></a>Funciones clasificadores de objetos  
 Visual Basic proporciona funciones que devuelven información sobre lo que hace referencia a una variable `Object`, como se muestra en la tabla siguiente.  
  
|Función|Devuelve true si la variable de objeto hace referencia a|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|Matriz de valores, en lugar de un valor único.|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|Un valor de [tipo de datos de fecha](../../../../visual-basic/language-reference/data-types/date-data-type.md) o una cadena que se puede interpretar como un valor de fecha y hora|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|Un objeto de tipo <xref:System.DBNull>, que representa datos que faltan o que no existen.|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|Un objeto de excepción, que se deriva de <xref:System.Exception>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|[Nothing](../../../../visual-basic/language-reference/nothing.md), es decir, no hay ningún objeto asignado actualmente a la variable.|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|Un número o una cadena que se puede interpretar como un número.|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|Un tipo de referencia (como una cadena, una matriz, un delegado o un tipo de clase)|  
  
 Puede utilizar estas funciones para evitar el envío de un valor no válido a una operación o un procedimiento.  
  
## <a name="typeof-operator"></a>Operador TypeOf  
 También puede usar el [operador typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) para determinar si una variable de objeto hace referencia actualmente a un tipo de datos específico. La expresión `TypeOf`... `Is` se evalúa como @no__t 2 Si el tipo en tiempo de ejecución del operando se deriva del tipo especificado o lo implementa.  
  
 En el ejemplo siguiente se usa `TypeOf` en variables de objeto que hacen referencia a tipos de valor y de referencia.  
  
```vb  
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
  
 En el ejemplo anterior se escriben las líneas siguientes en la ventana de **depuración** :  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 La variable de objeto `num` hace referencia a los datos de tipo `Integer` y `frm` hace referencia a un objeto de la clase <xref:System.Windows.Forms.Form>.  
  
## <a name="object-arrays"></a>Matrices de objetos  
 Puede declarar y usar una matriz de variables `Object`. Esto resulta útil cuando se necesita controlar una variedad de tipos de datos y clases de objetos. Todos los elementos de una matriz deben tener el mismo tipo de datos declarado. La declaración de este tipo de datos como `Object` permite almacenar objetos e instancias de clase junto con otros tipos de datos de la matriz.  
  
## <a name="see-also"></a>Vea también

- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Declaración de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Asignación de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Cómo: Haga referencia a la instancia actual de un objeto @ no__t-0
- [Cómo: Determinar el tipo al que hace referencia una variable de objeto @ no__t-0
- [Cómo: Determinar si dos objetos están relacionados @ no__t-0
- [Cómo: Determinar si dos objetos son idénticos @ no__t-0
- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
