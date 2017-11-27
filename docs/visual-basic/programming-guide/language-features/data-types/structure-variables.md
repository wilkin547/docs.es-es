---
title: Variables de estructura (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef42c44de84caffde909eb2b3e9361016a6abb97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="6c55e-102">Variables de estructura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c55e-102">Structure Variables (Visual Basic)</span></span>
<span data-ttu-id="6c55e-103">Una vez haya creado una estructura, puede declarar variables de nivel de procedimiento y el nivel de módulo como ese tipo.</span><span class="sxs-lookup"><span data-stu-id="6c55e-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="6c55e-104">Por ejemplo, puede crear una estructura que registra la información acerca de un sistema informático.</span><span class="sxs-lookup"><span data-stu-id="6c55e-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="6c55e-105">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="6c55e-105">The following example demonstrates this.</span></span>  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 <span data-ttu-id="6c55e-106">Ahora puede declarar variables de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="6c55e-106">You can now declare variables of that type.</span></span> <span data-ttu-id="6c55e-107">Esto ilustra en la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="6c55e-107">The following declaration illustrates this.</span></span>  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  <span data-ttu-id="6c55e-108">En las clases y módulos, las estructuras declaradas mediante la [Dim (instrucción)](../../../../visual-basic/language-reference/statements/dim-statement.md) predeterminado para el acceso público.</span><span class="sxs-lookup"><span data-stu-id="6c55e-108">In classes and modules, structures declared using the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="6c55e-109">Si piensa que una estructura sea privada, asegúrese de que se declara mediante la [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave.</span><span class="sxs-lookup"><span data-stu-id="6c55e-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword.</span></span>  
  
## <a name="access-to-structure-values"></a><span data-ttu-id="6c55e-110">Acceso a valores de estructura</span><span class="sxs-lookup"><span data-stu-id="6c55e-110">Access to Structure Values</span></span>  
 <span data-ttu-id="6c55e-111">Para asignar y recuperar valores de los elementos de una variable de estructura, utilice la misma sintaxis que se utilice para establecer y obtener propiedades de un objeto.</span><span class="sxs-lookup"><span data-stu-id="6c55e-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="6c55e-112">Coloque el operador de acceso de miembro (`.`) entre el nombre de variable de estructura y el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="6c55e-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="6c55e-113">En el ejemplo siguiente se tiene acceso a elementos de las variables declaradas previamente como tipo `systemInfo`.</span><span class="sxs-lookup"><span data-stu-id="6c55e-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a><span data-ttu-id="6c55e-114">Asignación de Variables de estructura</span><span class="sxs-lookup"><span data-stu-id="6c55e-114">Assigning Structure Variables</span></span>  
 <span data-ttu-id="6c55e-115">También puede asignar una variable a otro si ambos son del mismo tipo de estructura.</span><span class="sxs-lookup"><span data-stu-id="6c55e-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="6c55e-116">Esto copia todos los elementos de una estructura en los elementos correspondientes de la otra.</span><span class="sxs-lookup"><span data-stu-id="6c55e-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="6c55e-117">Esto ilustra en la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="6c55e-117">The following declaration illustrates this.</span></span>  
  
```  
yourSystem = mySystem  
```  
  
 <span data-ttu-id="6c55e-118">Si un elemento de estructura es un tipo de referencia, como un `String`, `Object`, o se copia la matriz, el puntero a los datos.</span><span class="sxs-lookup"><span data-stu-id="6c55e-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="6c55e-119">En el ejemplo anterior, si `systemInfo` hubiera incluido una variable de objeto, a continuación, en el ejemplo anterior se habría copiado el puntero de `mySystem` a `yourSystem`, y un cambio en los datos del objeto a través de una estructura estaría activo cuando se tiene acceso a través de la otra estructura.</span><span class="sxs-lookup"><span data-stu-id="6c55e-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c55e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c55e-120">See Also</span></span>  
 [<span data-ttu-id="6c55e-121">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="6c55e-121">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [<span data-ttu-id="6c55e-122">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="6c55e-122">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="6c55e-123">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="6c55e-123">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [<span data-ttu-id="6c55e-124">Tipos de valores y tipos de referencias</span><span class="sxs-lookup"><span data-stu-id="6c55e-124">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [<span data-ttu-id="6c55e-125">Estructuras</span><span class="sxs-lookup"><span data-stu-id="6c55e-125">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="6c55e-126">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="6c55e-126">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="6c55e-127">Declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="6c55e-127">How to: Declare a Structure</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [<span data-ttu-id="6c55e-128">Estructuras y otros elementos de programación</span><span class="sxs-lookup"><span data-stu-id="6c55e-128">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [<span data-ttu-id="6c55e-129">Estructuras y clases</span><span class="sxs-lookup"><span data-stu-id="6c55e-129">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [<span data-ttu-id="6c55e-130">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6c55e-130">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)
