---
title: "Of (Cl&#225;usula, Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Of"
  - "vb.Of"
  - "vb.of"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "argumentos [Visual Basic], tipos de datos"
  - "restricciones, tipos genéricos de Visual Basic"
  - "argumentos de tipo de datos"
  - "parámetros genéricos"
  - "genéricos [Visual Basic], restricciones"
  - "Of (palabra clave)"
  - "parámetros, genéricos"
  - "parámetros, tipo"
  - "parámetros de tipo"
  - "tipos [Visual Basic], genéricos"
ms.assetid: 0db8f65c-65af-4089-ab7f-6fcfecb60444
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Of (Cl&#225;usula, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Introduce una cláusula `Of` que identifica un *parámetro de tipo* en una clase, estructura, interfaz, delegado o procedimiento *genéricos*.   Para obtener información sobre los tipos genéricos, vea [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  
  
## Utilizar la palabra clave Of  
 El ejemplo de código siguiente utiliza la palabra clave `Of` para definir el contorno de una clase que acepta dos parámetros de tipo.  *Restringe* el parámetro `keyType` mediante la interfaz <xref:System.IComparable>, lo que significa que el código utilizado debe proporcionar un argumento de tipo que implemente <xref:System.IComparable>.  Esto es necesario para que el procedimiento `add` pueda llamar al método <xref:System.IComparable.CompareTo%2A?displayProperty=fullName>.  Para obtener más información sobre restricciones, vea [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md).  
  
```  
Public Class Dictionary(Of entryType, keyType As IComparable)  
    Public Sub add(ByVal e As entryType, ByVal k As keyType)  
        Dim dk As keyType  
        If k.CompareTo(dk) = 0 Then  
        End If  
    End Sub  
    Public Function find(ByVal k As keyType) As entryType  
    End Function  
End Class  
```  
  
 Si finaliza la definición de la clase anterior, puede construir una variedad de clases `dictionary` a partir de ella.  Los tipos que proporciona a `entryType` y `keyType` determinan qué tipo de entrada contiene la clase y qué tipo de clave asocia con cada entrada.  Debido a la restricción, debe proporcionar a `keyType` un tipo que implemente <xref:System.IComparable>.  
  
 El siguiente ejemplo de código crea un objeto que retiene las entradas `String` y asocia una clave `Integer` a cada uno.  `Integer` implementa <xref:System.IComparable> y por consiguiente satisface la restricción en `keyType`.  
  
```  
Dim d As New dictionary(Of String, Integer)  
```  
  
 La palabra clave `Of` se puede utilizar en estos contextos:  
  
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Delegate \(Instrucción\)](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 <xref:System.IComparable>   
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)