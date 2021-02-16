---
description: 'Más información sobre: estructuras y otros elementos de programación (Visual Basic)'
title: Estructuras y otros elementos de programación
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 62052389b617849566a3cd0c475a2eb5da9e61ca
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100430591"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>Estructuras y otros elementos de programación (Visual Basic)

Puede usar estructuras junto con matrices, objetos y procedimientos, así como entre sí. Las interacciones utilizan la misma sintaxis que estos elementos usan individualmente.  
  
> [!NOTE]
> No se puede inicializar ninguno de los elementos de la estructura en la declaración de la estructura. Solo puede asignar valores a los elementos de una variable que se ha declarado como un tipo de estructura.  
  
## <a name="structures-and-arrays"></a>Estructuras y matrices  

 Una estructura puede contener una matriz como uno o varios de sus elementos. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 Puede tener acceso a los valores de una matriz dentro de una estructura de la misma manera que tiene acceso a una propiedad en un objeto. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 También puede declarar una matriz de estructuras. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 Siga las mismas reglas para tener acceso a los componentes de esta arquitectura de datos. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>Estructuras y objetos  

 Una estructura puede contener un objeto como uno o varios de sus elementos. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 Debe utilizar una clase de objeto específica en una declaración de este tipo, en lugar de `Object` .  
  
## <a name="structures-and-procedures"></a>Estructuras y procedimientos  

 Puede pasar una estructura como un argumento de procedimiento. Esto se ilustra en el siguiente ejemplo:  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 En el ejemplo anterior se pasa la estructura *por referencia*, lo que permite al procedimiento modificar sus elementos para que los cambios surtan efecto en el código de llamada. Si desea proteger una estructura contra dicha modificación, pásela por valor.  
  
 También puede devolver una estructura a partir de un `Function` procedimiento. Esto se ilustra en el siguiente ejemplo:  
  
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
  
## <a name="structures-within-structures"></a>Estructuras dentro de estructuras  

 Las estructuras pueden contener otras estructuras. Esto se ilustra en el siguiente ejemplo:  
  
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
  
 También puede usar esta técnica para encapsular una estructura definida en un módulo dentro de una estructura definida en otro módulo.  
  
 Las estructuras pueden contener otras estructuras para una profundidad arbitraria.  
  
## <a name="see-also"></a>Consulte también

- [Tipo de datos](index.md)
- [Tipos de datos básicos](elementary-data-types.md)
- [Tipos de datos compuestos](composite-data-types.md)
- [Tipos de valor y tipos de referencia](value-types-and-reference-types.md)
- [Estructuras](structures.md)
- [Solución de problemas de los tipos de datos](troubleshooting-data-types.md)
- [Procedimiento Declaración de estructuras](how-to-declare-a-structure.md)
- [Variables de estructura](structure-variables.md)
- [Estructuras y clases](structures-and-classes.md)
- [Structure (Instrucción)](../../../language-reference/statements/structure-statement.md)
