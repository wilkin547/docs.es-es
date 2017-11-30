---
title: "Cómo: Determinar el tipo al que hace referencia una variable de objeto (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5dd6785ecd48be3f0455de63b9e3f13a485ddbb2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>Cómo: Determinar el tipo al que hace referencia una variable de objeto (Visual Basic)
Una variable de objeto contiene un puntero a datos que están almacenados en otro lugar. Puede cambiar el tipo de datos en tiempo de ejecución. En cualquier momento, puede usar el <xref:System.Type.GetTypeCode%2A> método para determinar el tipo de tiempo de ejecución actual, o la [del operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) para averiguar si este tipo en tiempo de ejecución es compatible con un tipo especificado.  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>Para determinar que el tipo exacto al que una variable de objeto actualmente hace referencia a  
  
1.  En la variable de objeto, llame a la <xref:System.Object.GetType%2A> método para recuperar un <xref:System.Type?displayProperty=nameWithType> objeto.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  En el <xref:System.Type?displayProperty=nameWithType> clase, llame al método compartido <xref:System.Type.GetTypeCode%2A> para recuperar la <xref:System.TypeCode> valor de enumeración para el tipo del objeto.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     Puede probar el <xref:System.TypeCode> valor de enumeración con cualquier miembros de enumeración son de interés, como `Double`.  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>Para determinar si un objeto es compatible con un tipo especificado el tipo de variable  
  
-   Use la `TypeOf` operador en combinación con la [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) para probar el objeto con un `TypeOf`... `Is` expresión.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     El `TypeOf`... `Is` expresión devuelve `True` si el objeto de tiempo de ejecución Value de tipo es compatible con el tipo especificado.  
  
     El criterio de compatibilidad depende de si el tipo especificado es una clase, estructura o interfaz. En general, los tipos son compatibles si el objeto es del mismo tipo como, hereda de o implementa el tipo especificado. Para obtener más información, consulte [del operador TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Tenga en cuenta que el tipo especificado no puede ser una variable o expresión. Debe ser el nombre de un tipo definido, como una clase, estructura o interfaz. Esto incluye los tipos intrínsecos como `Integer` y `String`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Object.GetType%2A>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Type.GetTypeCode%2A>  
 <xref:System.TypeCode>  
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Tipo de objeto de datos](../../../../visual-basic/language-reference/data-types/object-data-type.md)
