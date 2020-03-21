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
# <a name="structures-and-other-programming-elements-visual-basic"></a><span data-ttu-id="d1933-102">Estructuras y otros elementos de programación (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1933-102">Structures and Other Programming Elements (Visual Basic)</span></span>
<span data-ttu-id="d1933-103">Puede utilizar estructuras junto con matrices, objetos y procedimientos, así como entre sí.</span><span class="sxs-lookup"><span data-stu-id="d1933-103">You can use structures in conjunction with arrays, objects, and procedures, as well as with each other.</span></span> <span data-ttu-id="d1933-104">Las interacciones utilizan la misma sintaxis que estos elementos utilizan individualmente.</span><span class="sxs-lookup"><span data-stu-id="d1933-104">The interactions use the same syntax as these elements use individually.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1933-105">No se puede inicializar ninguno de los elementos de estructura en la declaración de estructura.</span><span class="sxs-lookup"><span data-stu-id="d1933-105">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="d1933-106">Puede asignar valores solo a elementos de una variable que se ha declarado como de un tipo de estructura.</span><span class="sxs-lookup"><span data-stu-id="d1933-106">You can assign values only to elements of a variable that has been declared to be of a structure type.</span></span>  
  
## <a name="structures-and-arrays"></a><span data-ttu-id="d1933-107">Estructuras y matrices</span><span class="sxs-lookup"><span data-stu-id="d1933-107">Structures and Arrays</span></span>  
 <span data-ttu-id="d1933-108">Una estructura puede contener una matriz como uno o varios de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="d1933-108">A structure can contain an array as one or more of its elements.</span></span> <span data-ttu-id="d1933-109">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1933-109">The following example illustrates this.</span></span>  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 <span data-ttu-id="d1933-110">Tiene acceso a los valores de una matriz dentro de una estructura de la misma manera que tiene acceso a una propiedad en un objeto.</span><span class="sxs-lookup"><span data-stu-id="d1933-110">You access the values of an array within a structure the same way you access a property on an object.</span></span> <span data-ttu-id="d1933-111">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1933-111">The following example illustrates this.</span></span>  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 <span data-ttu-id="d1933-112">También puede declarar una matriz de estructuras.</span><span class="sxs-lookup"><span data-stu-id="d1933-112">You can also declare an array of structures.</span></span> <span data-ttu-id="d1933-113">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1933-113">The following example illustrates this.</span></span>  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 <span data-ttu-id="d1933-114">Siga las mismas reglas para acceder a los componentes de esta arquitectura de datos.</span><span class="sxs-lookup"><span data-stu-id="d1933-114">You follow the same rules to access the components of this data architecture.</span></span> <span data-ttu-id="d1933-115">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1933-115">The following example illustrates this.</span></span>  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a><span data-ttu-id="d1933-116">Estructuras y Objetos</span><span class="sxs-lookup"><span data-stu-id="d1933-116">Structures and Objects</span></span>  
 <span data-ttu-id="d1933-117">Una estructura puede contener un objeto como uno o varios de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="d1933-117">A structure can contain an object as one or more of its elements.</span></span> <span data-ttu-id="d1933-118">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1933-118">The following example illustrates this.</span></span>  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 <span data-ttu-id="d1933-119">Debe utilizar una clase de objeto específica `Object`en una declaración de este tipo, en lugar de .</span><span class="sxs-lookup"><span data-stu-id="d1933-119">You should use a specific object class in such a declaration, rather than `Object`.</span></span>  
  
## <a name="structures-and-procedures"></a><span data-ttu-id="d1933-120">Estructuras y procedimientos</span><span class="sxs-lookup"><span data-stu-id="d1933-120">Structures and Procedures</span></span>  
 <span data-ttu-id="d1933-121">Puede pasar una estructura como argumento de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d1933-121">You can pass a structure as a procedure argument.</span></span> <span data-ttu-id="d1933-122">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1933-122">The following example illustrates this.</span></span>  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 <span data-ttu-id="d1933-123">En el ejemplo anterior se pasa la estructura *por referencia*, lo que permite que el procedimiento modifique sus elementos para que los cambios surtan efecto en el código de llamada.</span><span class="sxs-lookup"><span data-stu-id="d1933-123">The preceding example passes the structure *by reference*, which allows the procedure to modify its elements so that the changes take effect in the calling code.</span></span> <span data-ttu-id="d1933-124">Si desea proteger una estructura contra dicha modificación, pásela por valor.</span><span class="sxs-lookup"><span data-stu-id="d1933-124">If you want to protect a structure against such modification, pass it by value.</span></span>  
  
 <span data-ttu-id="d1933-125">También puede devolver una `Function` estructura de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d1933-125">You can also return a structure from a `Function` procedure.</span></span> <span data-ttu-id="d1933-126">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1933-126">The following example illustrates this.</span></span>  
  
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
  
## <a name="structures-within-structures"></a><span data-ttu-id="d1933-127">Estructuras dentro de las estructuras</span><span class="sxs-lookup"><span data-stu-id="d1933-127">Structures Within Structures</span></span>  
 <span data-ttu-id="d1933-128">Las estructuras pueden contener otras estructuras.</span><span class="sxs-lookup"><span data-stu-id="d1933-128">Structures can contain other structures.</span></span> <span data-ttu-id="d1933-129">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d1933-129">The following example illustrates this.</span></span>  
  
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
  
 <span data-ttu-id="d1933-130">También puede utilizar esta técnica para encapsular una estructura definida en un módulo dentro de una estructura definida en un módulo diferente.</span><span class="sxs-lookup"><span data-stu-id="d1933-130">You can also use this technique to encapsulate a structure defined in one module within a structure defined in a different module.</span></span>  
  
 <span data-ttu-id="d1933-131">Las estructuras pueden contener otras estructuras a una profundidad arbitraria.</span><span class="sxs-lookup"><span data-stu-id="d1933-131">Structures can contain other structures to an arbitrary depth.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1933-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1933-132">See also</span></span>

- [<span data-ttu-id="d1933-133">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="d1933-133">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="d1933-134">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="d1933-134">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="d1933-135">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="d1933-135">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="d1933-136">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="d1933-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="d1933-137">Estructuras</span><span class="sxs-lookup"><span data-stu-id="d1933-137">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="d1933-138">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="d1933-138">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="d1933-139">Cómo: Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="d1933-139">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [<span data-ttu-id="d1933-140">Variables de estructura</span><span class="sxs-lookup"><span data-stu-id="d1933-140">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="d1933-141">Estructuras y clases</span><span class="sxs-lookup"><span data-stu-id="d1933-141">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="d1933-142">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d1933-142">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
