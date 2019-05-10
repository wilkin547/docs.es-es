---
title: Procedimiento Determinar el tipo hace referencia una Variable de objeto (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 4ae73e6b3dec7864eb670bed67630b1cc96e5e61
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663548"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Procedimiento Determinar el tipo hace referencia una Variable de objeto (Visual Basic)
Una variable de objeto contiene un puntero a los datos que se almacenan en otro lugar. Puede cambiar el tipo de los datos durante el tiempo de ejecución. En cualquier momento, puede usar el <xref:System.Type.GetTypeCode%2A> método para determinar el tipo de tiempo de ejecución actual, o la [operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) para averiguar si el actual, tipo de tiempo de ejecución es compatible con un tipo especificado.  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Para determinar que el tipo exacto una variable de objeto actualmente hace referencia a  
  
1. En la variable de objeto, llame a la <xref:System.Object.GetType%2A> método para recuperar un <xref:System.Type?displayProperty=nameWithType> objeto.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2. En el <xref:System.Type?displayProperty=nameWithType> clase, llame al método compartido <xref:System.Type.GetTypeCode%2A> para recuperar el <xref:System.TypeCode> valor de enumeración para el tipo del objeto.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     Puede probar la <xref:System.TypeCode> contra cualquier miembros de enumeración son de interés, como valor de la enumeración `Double`.  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Para determinar si un objeto es compatible con un tipo especificado el tipo de variable  
  
- Use la `TypeOf` operador en combinación con la [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) para probar el objeto con un `TypeOf`... `Is` expresión.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     El `TypeOf`... `Is` expresión devuelve `True` si el objeto de tiempo de ejecución Value de tipo es compatible con el tipo especificado.  
  
     El criterio para la compatibilidad depende de si el tipo especificado es una clase, estructura o interfaz. En general, los tipos son compatibles si el objeto es del mismo tipo que, hereda o implementa el tipo especificado. Para obtener más información, consulte [operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Tenga en cuenta que el tipo especificado no puede ser una variable o expresión. Debe ser el nombre de un tipo definido, por ejemplo, una clase, estructura o interfaz. Esto incluye tipos intrínsecos como `Integer` y `String`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
