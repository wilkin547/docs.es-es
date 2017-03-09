---
title: "Estructuras y otros elementos de programaci&#243;n (Visual Basic) | Microsoft Docs"
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
  - "matrices [Visual Basic], elementos de estructura"
  - "estructuras anidadas"
  - "objetos [Visual Basic], elementos de estructura"
  - "procedimientos, estructuras como argumentos"
  - "estructuras, matrices"
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Estructuras y otros elementos de programaci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se pueden utilizar estructuras conjuntamente con matrices, objetos y procedimientos, así como unos con otros.  Las interacciones utilizan la misma sintaxis que utilizan estos elementos de forma individual.  
  
> [!NOTE]
>  No puede inicializar ninguno de los elementos de la estructura en la declaración de la estructura.  Sólo se pueden asignar valores a los elementos de una variable que se ha declarado como del tipo estructura.  
  
## Estructuras y matrices  
 Una estructura puede contener una matriz como uno o más de sus elementos.  Esto se ilustra en el siguiente ejemplo:  
  
```vb#  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 Tiene acceso a los valores de una matriz dentro de una estructura de la misma manera que tiene acceso a una propiedad en un objeto.  Esto se ilustra en el siguiente ejemplo:  
  
```vb#  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 También puede declarar una matriz de estructuras.  Esto se ilustra en el siguiente ejemplo:  
  
```vb#  
Dim allSystems(100) As systemInfo  
```  
  
 Se siguen las mismas reglas para tener acceso a los componentes de esta arquitectura de datos.  Esto se ilustra en el siguiente ejemplo:  
  
```vb#  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## Estructuras y objetos  
 Una estructura puede contener un objeto como uno o más de sus elementos.  Esto se ilustra en el siguiente ejemplo:  
  
```vb#  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 Se puede utilizar una clase de objeto específica en este tipo de declaración, en lugar de `Object`.  
  
## Estructuras y procedimientos  
 Puede pasar una estructura como un argumento de procedimiento.  Esto se ilustra en el siguiente ejemplo:  
  
```vb#  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 El ejemplo anterior pasa la estructura *por referencia*, lo que permite al procedimiento modificar sus elementos de tal forma que los cambios se hacen  efectivos en el código de llamada.  Si desea proteger una estructura frente a una modificación de este tipo, pásela por valor.  
  
 También puede devolver una estructura de un procedimiento `Function`.  Esto se ilustra en el siguiente ejemplo:  
  
```vb#  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## Estructuras dentro de estructuras  
 Las estructuras pueden contener otras estructuras.  Esto se ilustra en el siguiente ejemplo:  
  
```vb#  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb#  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 También puede utilizar esta técnica para encapsular una estructura definida en un módulo dentro de una estructura definida en un módulo distinto.  
  
 Las estructuras pueden contener otras estructuras hasta cualquier nivel.  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de datos elementales](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Variables de estructura](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)   
 [Estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Structure \(Instrucción\)](../../../../visual-basic/language-reference/statements/structure-statement.md)