---
title: Estructuras y otros elementos de programación
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 73d3f999e95c484dff3f5409f2cdb9032b64fe38
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266864"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>Estructuras y otros elementos de programación (Visual Basic)
Puede utilizar estructuras junto con matrices, objetos y procedimientos, así como entre sí. Las interacciones utilizan la misma sintaxis que estos elementos utilizan individualmente.  
  
> [!NOTE]
> No se puede inicializar ninguno de los elementos de estructura en la declaración de estructura. Puede asignar valores solo a elementos de una variable que se ha declarado como de un tipo de estructura.  
  
## <a name="structures-and-arrays"></a>Estructuras y matrices  
 Una estructura puede contener una matriz como uno o varios de sus elementos. Esto se ilustra en el siguiente ejemplo.  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 Tiene acceso a los valores de una matriz dentro de una estructura de la misma manera que tiene acceso a una propiedad en un objeto. Esto se ilustra en el siguiente ejemplo.  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 También puede declarar una matriz de estructuras. Esto se ilustra en el siguiente ejemplo.  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 Siga las mismas reglas para acceder a los componentes de esta arquitectura de datos. Esto se ilustra en el siguiente ejemplo.  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>Estructuras y Objetos  
 Una estructura puede contener un objeto como uno o varios de sus elementos. Esto se ilustra en el siguiente ejemplo.  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 Debe utilizar una clase de objeto específica `Object`en una declaración de este tipo, en lugar de .  
  
## <a name="structures-and-procedures"></a>Estructuras y procedimientos  
 Puede pasar una estructura como argumento de procedimiento. Esto se ilustra en el siguiente ejemplo.  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 En el ejemplo anterior se pasa la estructura *por referencia*, lo que permite que el procedimiento modifique sus elementos para que los cambios surtan efecto en el código de llamada. Si desea proteger una estructura contra dicha modificación, pásela por valor.  
  
 También puede devolver una `Function` estructura de un procedimiento. Esto se ilustra en el siguiente ejemplo.  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a>Estructuras dentro de las estructuras  
 Las estructuras pueden contener otras estructuras. Esto se ilustra en el siguiente ejemplo.  
  
```vb  
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
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 También puede utilizar esta técnica para encapsular una estructura definida en un módulo dentro de una estructura definida en un módulo diferente.  
  
 Las estructuras pueden contener otras estructuras a una profundidad arbitraria.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Tipos de datos básicos](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipos de datos compuestos](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Cómo: Declarar una estructura](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Variables de estructura](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure (Instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md)
