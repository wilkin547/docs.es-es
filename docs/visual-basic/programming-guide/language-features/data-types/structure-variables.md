---
title: Variables de estructura
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 270e8ca26185e4a68def3b95f4ce6ab4c57a629c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393590"
---
# <a name="structure-variables-visual-basic"></a><span data-ttu-id="44360-102">Variables de estructura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44360-102">Structure Variables (Visual Basic)</span></span>

<span data-ttu-id="44360-103">Una vez creada una estructura, puede declarar variables de nivel de procedimiento y de nivel de módulo como ese tipo.</span><span class="sxs-lookup"><span data-stu-id="44360-103">Once you have created a structure, you can declare procedure-level and module-level variables as that type.</span></span> <span data-ttu-id="44360-104">Por ejemplo, puede crear una estructura que registre información sobre un sistema informático.</span><span class="sxs-lookup"><span data-stu-id="44360-104">For example, you can create a structure that records information about a computer system.</span></span> <span data-ttu-id="44360-105">El ejemplo siguiente demuestra este patrón.</span><span class="sxs-lookup"><span data-stu-id="44360-105">The following example demonstrates this.</span></span>

```vb
Public Structure systemInfo
    Public cPU As String
    Public memory As Long
    Public purchaseDate As Date
End Structure
```

<span data-ttu-id="44360-106">Ahora puede declarar variables de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="44360-106">You can now declare variables of that type.</span></span> <span data-ttu-id="44360-107">La siguiente declaración ilustra esto.</span><span class="sxs-lookup"><span data-stu-id="44360-107">The following declaration illustrates this.</span></span>

```vb
Dim mySystem, yourSystem As systemInfo
```

> [!NOTE]
> <span data-ttu-id="44360-108">En las clases y los módulos, las estructuras declaradas con la [instrucción Dim](../../../language-reference/statements/dim-statement.md) tienen como valor predeterminado el acceso público.</span><span class="sxs-lookup"><span data-stu-id="44360-108">In classes and modules, structures declared using the [Dim Statement](../../../language-reference/statements/dim-statement.md) default to public access.</span></span> <span data-ttu-id="44360-109">Si desea que una estructura sea privada, asegúrese de que la declara mediante la palabra clave [Private](../../../language-reference/modifiers/private.md) .</span><span class="sxs-lookup"><span data-stu-id="44360-109">If you intend a structure to be private, make sure you declare it using the [Private](../../../language-reference/modifiers/private.md) keyword.</span></span>

## <a name="access-to-structure-values"></a><span data-ttu-id="44360-110">Acceso a los valores de la estructura</span><span class="sxs-lookup"><span data-stu-id="44360-110">Access to Structure Values</span></span>

<span data-ttu-id="44360-111">Para asignar y recuperar valores de los elementos de una variable de estructura, se usa la misma sintaxis que se usa para establecer y obtener propiedades en un objeto.</span><span class="sxs-lookup"><span data-stu-id="44360-111">To assign and retrieve values from the elements of a structure variable, you use the same syntax as you use to set and get properties on an object.</span></span> <span data-ttu-id="44360-112">Coloque el operador de acceso a miembros ( `.` ) entre el nombre de la variable de estructura y el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="44360-112">You place the member access operator (`.`) between the structure variable name and the element name.</span></span> <span data-ttu-id="44360-113">En el ejemplo siguiente se obtiene acceso a los elementos de las variables declaradas previamente como tipo `systemInfo` .</span><span class="sxs-lookup"><span data-stu-id="44360-113">The following example accesses elements of the variables previously declared as type `systemInfo`.</span></span>

```vb
mySystem.cPU = "486"
Dim tooOld As Boolean
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True
```

## <a name="assigning-structure-variables"></a><span data-ttu-id="44360-114">Asignar variables de estructura</span><span class="sxs-lookup"><span data-stu-id="44360-114">Assigning Structure Variables</span></span>

<span data-ttu-id="44360-115">También puede asignar una variable a otra si ambos son del mismo tipo de estructura.</span><span class="sxs-lookup"><span data-stu-id="44360-115">You can also assign one variable to another if both are of the same structure type.</span></span> <span data-ttu-id="44360-116">Esto copia todos los elementos de una estructura en los elementos correspondientes de la otra.</span><span class="sxs-lookup"><span data-stu-id="44360-116">This copies all the elements of one structure to the corresponding elements in the other.</span></span> <span data-ttu-id="44360-117">La siguiente declaración ilustra esto.</span><span class="sxs-lookup"><span data-stu-id="44360-117">The following declaration illustrates this.</span></span>

```vb
yourSystem = mySystem
```

<span data-ttu-id="44360-118">Si un elemento de estructura es un tipo de referencia, como `String` una `Object` matriz, o, se copia el puntero a los datos.</span><span class="sxs-lookup"><span data-stu-id="44360-118">If a structure element is a reference type, such as a `String`, `Object`, or array, the pointer to the data is copied.</span></span> <span data-ttu-id="44360-119">En el ejemplo anterior, si `systemInfo` hubiera incluido una variable de objeto, el ejemplo anterior habría copiado el puntero de `mySystem` a `yourSystem` , y un cambio en los datos del objeto a través de una estructura sería efectivo al obtener acceso a través de la otra estructura.</span><span class="sxs-lookup"><span data-stu-id="44360-119">In the previous example, if `systemInfo` had included an object variable, then the preceding example would have copied the pointer from `mySystem` to `yourSystem`, and a change to the object's data through one structure would be in effect when accessed through the other structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="44360-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="44360-120">See also</span></span>

- [<span data-ttu-id="44360-121">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="44360-121">Data Types</span></span>](index.md)
- [<span data-ttu-id="44360-122">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="44360-122">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="44360-123">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="44360-123">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="44360-124">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="44360-124">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="44360-125">Estructuras</span><span class="sxs-lookup"><span data-stu-id="44360-125">Structures</span></span>](structures.md)
- [<span data-ttu-id="44360-126">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="44360-126">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="44360-127">Procedimiento Declaración de estructuras</span><span class="sxs-lookup"><span data-stu-id="44360-127">How to: Declare a Structure</span></span>](how-to-declare-a-structure.md)
- [<span data-ttu-id="44360-128">Estructuras y otros elementos de programación</span><span class="sxs-lookup"><span data-stu-id="44360-128">Structures and Other Programming Elements</span></span>](structures-and-other-programming-elements.md)
- [<span data-ttu-id="44360-129">Estructuras y clases</span><span class="sxs-lookup"><span data-stu-id="44360-129">Structures and Classes</span></span>](structures-and-classes.md)
- [<span data-ttu-id="44360-130">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="44360-130">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
