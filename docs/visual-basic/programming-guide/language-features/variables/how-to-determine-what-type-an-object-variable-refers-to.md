---
title: "C&#243;mo: Determinar el tipo al que hace referencia una variable de objeto (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables de objeto, determinar tipo"
  - "TypeOf (operador) [Visual Basic], determinar tipo de variables de objeto"
  - "variables [Visual Basic], objeto"
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Determinar el tipo al que hace referencia una variable de objeto (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Una variable de objeto contiene un puntero a datos que se almacenan en otra parte.  El tipo de estos datos puede cambiar durante el tiempo de ejecución.  En cualquier momento, puede utilizar el método <xref:System.Type.GetTypeCode%2A> para determinar el tipo en tiempo de ejecución actual o [TypeOf \(Operador\)](../../../../visual-basic/language-reference/operators/typeof-operator.md) para averiguar si el tipo en tiempo de ejecución actual es compatible con un tipo especificado.  
  
### Para determinar el tipo exacto al que una variable de objeto hace referencia actualmente  
  
1.  En la variable de objeto, llame al método <xref:System.Object.GetType%2A> para recuperar un objeto <xref:System.Type?displayProperty=fullName>.  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2.  En la clase <xref:System.Type?displayProperty=fullName>, llame al método <xref:System.Type.GetTypeCode%2A> compartido para recuperar el valor de enumeración <xref:System.TypeCode> para el tipo del objeto.  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     Puede probar el valor de enumeración <xref:System.TypeCode> con los miembros de enumeración que sean de su interés, como `Double`.  
  
### Para determinar si el tipo de una variable de objeto es compatible con un tipo especificado  
  
-   Utilice al operador `TypeOf` en combinación con [Is \(Operador\)](../../../../visual-basic/language-reference/operators/is-operator.md) para probar el objeto con una expresión `TypeOf`...`Is`.  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     La expresión `TypeOf`...`Is` devuelve `True` si el tipo del objeto en tiempo de ejecución es compatible con el tipo especificado.  
  
     El criterio para la compatibilidad depende de si el tipo especificado es una clase, estructura o interfaz.  En general, los tipos son compatibles si el objeto es del mismo tipo que hereda o implementa el tipo especificado.  Para obtener más información, vea [TypeOf \(Operador\)](../../../../visual-basic/language-reference/operators/typeof-operator.md).  
  
## Compilar el código  
 Observe que el tipo especificado no puede ser una variable o expresión.  Debe ser el nombre de un tipo definido, como una clase, estructura o interfaz.  Esto incluye los tipos intrínsecos como `Integer` y `String`.  
  
## Vea también  
 <xref:System.Object.GetType%2A>   
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Type.GetTypeCode%2A>   
 <xref:System.TypeCode>   
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Valores de las variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Object \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/object-data-type.md)