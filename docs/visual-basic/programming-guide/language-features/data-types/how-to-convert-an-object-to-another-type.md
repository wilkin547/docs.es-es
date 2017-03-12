---
title: "C&#243;mo: Convertir un objeto en otro tipo en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "objetos [Visual Basic], convertir"
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# C&#243;mo: Convertir un objeto en otro tipo en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Convierte una variable `Object` en otro tipo de datos utilizando una palabra clave de conversión como [CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## Ejemplo  
 En el ejemplo siguiente se convierte una variable de tipo `Object` en `Integer` y `String`.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Si sabe que el contenido de una variable `Object` es de un tipo de datos determinado, es mejor convertir la variable en ese tipo de datos.  Si sigue utilizando la variable `Object`, provoca una *conversión boxing* y una *conversión unboxing* \(para un tipo de valor\) o un *enlace en tiempo de ejecución* \(para un tipo de referencia\).  Estas operaciones exigen todas un tiempo de ejecución adicional y ralentizan el rendimiento.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Object>   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversiones entre cadenas y otros tipos](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [Conversiones de matrices](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)