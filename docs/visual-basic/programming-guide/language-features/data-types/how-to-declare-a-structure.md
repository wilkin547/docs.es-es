---
description: 'Más información acerca de cómo: declarar una estructura (Visual Basic)'
title: Procedimiento Declaración de estructuras
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 7560f22db70fd5804ca309720d32477bcb9a3782
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436934"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="2f56f-103">Cómo: Declarar una estructura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2f56f-103">How to: Declare a Structure (Visual Basic)</span></span>

<span data-ttu-id="2f56f-104">Comienza una declaración de estructura con la [instrucción Structure](../../../language-reference/statements/structure-statement.md)y la finaliza con la `End Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="2f56f-104">You begin a structure declaration with the [Structure Statement](../../../language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="2f56f-105">Entre estas dos instrucciones debe declarar al menos un *elemento*.</span><span class="sxs-lookup"><span data-stu-id="2f56f-105">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="2f56f-106">Los elementos pueden ser de cualquier tipo de datos, pero al menos uno debe ser una variable no compartida o un evento no personalizado no compartido.</span><span class="sxs-lookup"><span data-stu-id="2f56f-106">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="2f56f-107">No se puede inicializar ninguno de los elementos de la estructura en la declaración de la estructura.</span><span class="sxs-lookup"><span data-stu-id="2f56f-107">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="2f56f-108">Cuando se declara una variable para que sea de un tipo de estructura, se asignan valores a los elementos accediendo a ellas a través de la variable.</span><span class="sxs-lookup"><span data-stu-id="2f56f-108">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="2f56f-109">Para obtener una explicación de las diferencias entre las estructuras y las clases, vea [estructuras y clases](structures-and-classes.md).</span><span class="sxs-lookup"><span data-stu-id="2f56f-109">For a discussion of the differences between structures and classes, see [Structures and Classes](structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="2f56f-110">Para fines de demostración, considere una situación en la que desea realizar un seguimiento del nombre de un empleado, la extensión de teléfono y el salario.</span><span class="sxs-lookup"><span data-stu-id="2f56f-110">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="2f56f-111">Una estructura le permite hacer esto en una sola variable.</span><span class="sxs-lookup"><span data-stu-id="2f56f-111">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="2f56f-112">Para declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="2f56f-112">To declare a structure</span></span>  
  
1. <span data-ttu-id="2f56f-113">Cree las instrucciones de inicio y finalización de la estructura.</span><span class="sxs-lookup"><span data-stu-id="2f56f-113">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="2f56f-114">Puede especificar el nivel de acceso de una estructura mediante la palabra clave [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)o [Private](../../../language-reference/modifiers/private.md) , o puede dejar que sea el valor predeterminado `Public` .</span><span class="sxs-lookup"><span data-stu-id="2f56f-114">You can specify the access level of a structure using the [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md), or [Private](../../../language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="2f56f-115">Agregue elementos al cuerpo de la estructura.</span><span class="sxs-lookup"><span data-stu-id="2f56f-115">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="2f56f-116">Una estructura debe tener al menos un elemento.</span><span class="sxs-lookup"><span data-stu-id="2f56f-116">A structure must have at least one element.</span></span> <span data-ttu-id="2f56f-117">Debe declarar cada elemento y especificar un nivel de acceso para él.</span><span class="sxs-lookup"><span data-stu-id="2f56f-117">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="2f56f-118">Si usa la [instrucción Dim](../../../language-reference/statements/dim-statement.md) sin palabras clave, el valor predeterminado de accesibilidad es `Public` .</span><span class="sxs-lookup"><span data-stu-id="2f56f-118">If you use the [Dim Statement](../../../language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     <span data-ttu-id="2f56f-119">El `salary` campo del ejemplo anterior es `Private` , lo que significa que es inaccesible fuera de la estructura, incluso desde la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="2f56f-119">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="2f56f-120">Sin embargo, el `giveRaise` procedimiento es `Public` , por lo que se puede llamar desde fuera de la estructura.</span><span class="sxs-lookup"><span data-stu-id="2f56f-120">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="2f56f-121">Del mismo modo, puede generar el `salaryReviewTime` evento desde fuera de la estructura.</span><span class="sxs-lookup"><span data-stu-id="2f56f-121">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="2f56f-122">Además de las variables, `Sub` procedimientos y eventos, también puede definir constantes, `Function` procedimientos y propiedades en una estructura.</span><span class="sxs-lookup"><span data-stu-id="2f56f-122">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="2f56f-123">Puede designar como máximo una propiedad como la *propiedad predeterminada*, siempre que tome al menos un argumento.</span><span class="sxs-lookup"><span data-stu-id="2f56f-123">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="2f56f-124">Puede controlar un evento con un procedimiento [compartido](../../../language-reference/modifiers/shared.md) `Sub` .</span><span class="sxs-lookup"><span data-stu-id="2f56f-124">You can handle an event with a [Shared](../../../language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="2f56f-125">Para obtener más información, vea [Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic](../procedures/how-to-declare-and-call-a-default-property.md).</span><span class="sxs-lookup"><span data-stu-id="2f56f-125">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f56f-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2f56f-126">See also</span></span>

- [<span data-ttu-id="2f56f-127">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="2f56f-127">Data Types</span></span>](index.md)
- [<span data-ttu-id="2f56f-128">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="2f56f-128">Elementary Data Types</span></span>](elementary-data-types.md)
- [<span data-ttu-id="2f56f-129">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="2f56f-129">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="2f56f-130">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="2f56f-130">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
- [<span data-ttu-id="2f56f-131">Estructuras</span><span class="sxs-lookup"><span data-stu-id="2f56f-131">Structures</span></span>](structures.md)
- [<span data-ttu-id="2f56f-132">Solución de problemas de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="2f56f-132">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
- [<span data-ttu-id="2f56f-133">Variables de estructura</span><span class="sxs-lookup"><span data-stu-id="2f56f-133">Structure Variables</span></span>](structure-variables.md)
- [<span data-ttu-id="2f56f-134">Estructuras y otros elementos de programación</span><span class="sxs-lookup"><span data-stu-id="2f56f-134">Structures and Other Programming Elements</span></span>](structures-and-other-programming-elements.md)
- [<span data-ttu-id="2f56f-135">Estructuras y clases</span><span class="sxs-lookup"><span data-stu-id="2f56f-135">Structures and Classes</span></span>](structures-and-classes.md)
- [<span data-ttu-id="2f56f-136">Tipo de datos definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="2f56f-136">User-Defined Data Type</span></span>](../../../language-reference/data-types/user-defined-data-type.md)
