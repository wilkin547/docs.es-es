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
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="64d20-103">Estructuras y otros elementos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64d20-103">Structures and Other Programming Elements (Visual Basic)</span></span>

<span data-ttu-id="64d20-104">Puede usar estructuras junto con matrices, objetos y procedimientos, así como entre sí.</span><span class="sxs-lookup"><span data-stu-id="64d20-104">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="64d20-105">Las interacciones utilizan la misma sintaxis que estos elementos usan individualmente.</span><span class="sxs-lookup"><span data-stu-id="64d20-105">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64d20-106">No se puede inicializar ninguno de los elementos de la estructura en la declaración de la estructura.</span><span class="sxs-lookup"><span data-stu-id="64d20-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="64d20-107">Solo puede asignar valores a los elementos de una variable que se ha declarado como un tipo de estructura.</span><span class="sxs-lookup"><span data-stu-id="64d20-107">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="64d20-108">Estructuras y matrices</span><span class="sxs-lookup"><span data-stu-id="64d20-108">Structures and Arrays</span></span>  

 <span data-ttu-id="64d20-109">Una estructura puede contener una matriz como uno o varios de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="64d20-109">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="64d20-110">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64d20-110">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 <span data-ttu-id="64d20-111">Puede tener acceso a los valores de una matriz dentro de una estructura de la misma manera que tiene acceso a una propiedad en un objeto.</span><span class="sxs-lookup"><span data-stu-id="64d20-111">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="64d20-112">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64d20-112">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="64d20-113">También puede declarar una matriz de estructuras.</span><span class="sxs-lookup"><span data-stu-id="64d20-113">You can also declare an array of structures.</span></span> <span data-ttu-id="64d20-114">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64d20-114">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="64d20-115">Siga las mismas reglas para tener acceso a los componentes de esta arquitectura de datos.</span><span class="sxs-lookup"><span data-stu-id="64d20-115">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="64d20-116">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64d20-116">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="64d20-117">Estructuras y objetos</span><span class="sxs-lookup"><span data-stu-id="64d20-117">Structures and Objects</span></span>  

 <span data-ttu-id="64d20-118">Una estructura puede contener un objeto como uno o varios de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="64d20-118">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="64d20-119">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64d20-119">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="64d20-120">Debe utilizar una clase de objeto específica en una declaración de este tipo, en lugar de `Object` .</span><span class="sxs-lookup"><span data-stu-id="64d20-120">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="64d20-121">Estructuras y procedimientos</span><span class="sxs-lookup"><span data-stu-id="64d20-121">Structures and Procedures</span></span>  

 <span data-ttu-id="64d20-122">Puede pasar una estructura como un argumento de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="64d20-122">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="64d20-123">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64d20-123">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="64d20-124">En el ejemplo anterior se pasa la estructura *por referencia*, lo que permite al procedimiento modificar sus elementos para que los cambios surtan efecto en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="64d20-124">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="64d20-125">Si desea proteger una estructura contra dicha modificación, pásela por valor.</span><span class="sxs-lookup"><span data-stu-id="64d20-125">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="64d20-126">También puede devolver una estructura a partir de un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="64d20-126">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="64d20-127">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64d20-127">The following example illustrates this.</span></span>  
  
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
  
## <a name="structures-within-structures"></a><span data-ttu-id="64d20-128">Estructuras dentro de estructuras</span><span class="sxs-lookup"><span data-stu-id="64d20-128">Structures Within Structures</span></span>  

 <span data-ttu-id="64d20-129">Las estructuras pueden contener otras estructuras.</span><span class="sxs-lookup"><span data-stu-id="64d20-129">Structures can contain other structures.</span></span> <span data-ttu-id="64d20-130">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="64d20-130">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="64d20-131">También puede usar esta técnica para encapsular una estructura definida en un módulo dentro de una estructura definida en otro módulo.</span><span class="sxs-lookup"><span data-stu-id="64d20-131">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="64d20-132">Las estructuras pueden contener otras estructuras para una profundidad arbitraria.</span><span class="sxs-lookup"><span data-stu-id="64d20-132">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d20-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64d20-133">See also</span></span>

- [<span data-ttu-id="64d20-134">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="64d20-134">Data Types</span></span>](index.md)
- [<span data-ttu-id="64d20-135">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="64d20-135">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="64d20-136">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="64d20-136">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="64d20-137">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="64d20-137">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="64d20-138">Estructuras</span><span class="sxs-lookup"><span data-stu-id="64d20-138">Structures</span></span>](structures.md)
- [<span data-ttu-id="64d20-139">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="64d20-139">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="64d20-140">Procedimiento Declaración de estructuras</span><span class="sxs-lookup"><span data-stu-id="64d20-140">How to: Declare a Structure</span></span>](how-to-declare-a-structure.md)
- [<span data-ttu-id="64d20-141">Variables de estructura</span><span class="sxs-lookup"><span data-stu-id="64d20-141">Structure Variables</span></span>](structure-variables.md)
- [<span data-ttu-id="64d20-142">Estructuras y clases</span><span class="sxs-lookup"><span data-stu-id="64d20-142">Structures and Classes</span></span>](structures-and-classes.md)
- [<span data-ttu-id="64d20-143">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="64d20-143">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
