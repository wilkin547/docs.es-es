---
title: Procedimiento Declarar una estructura (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: bfed5c969466cb427e6c94d39bfcc6a6e007c320
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672050"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="7bf7b-102">Procedimiento Declarar una estructura (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7bf7b-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="7bf7b-103">Comenzar una declaración structure con la [Structure (instrucción)](../../../../visual-basic/language-reference/statements/structure-statement.md), y finaliza con la `End` `Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End` `Structure` statement.</span></span> <span data-ttu-id="7bf7b-104">Entre estas dos instrucciones debe declarar al menos una *elemento*.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="7bf7b-105">Los elementos pueden ser de cualquier tipo de datos, pero al menos uno debe ser una variable no compartida o un evento no compartido, no personalizado.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="7bf7b-106">No se puede inicializar cualquiera de los elementos de estructura en la declaración de estructura.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="7bf7b-107">Cuando se declara una variable para que sea un tipo de estructura, asignar valores a los elementos mediante el acceso a ellos a través de la variable.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="7bf7b-108">Para obtener una explicación de las diferencias entre clases y estructuras, vea [estructuras y clases](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span><span class="sxs-lookup"><span data-stu-id="7bf7b-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="7bf7b-109">Para fines de demostración, considere una situación donde desea realizar un seguimiento de nombre, extensión telefónica y salario del empleado.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="7bf7b-110">Una estructura le permite hacer esto en una única variable.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="7bf7b-111">Para declarar una estructura</span><span class="sxs-lookup"><span data-stu-id="7bf7b-111">To declare a structure</span></span>  
  
1.  <span data-ttu-id="7bf7b-112">Cree el comienzo y finalización de instrucciones para la estructura.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="7bf7b-113">Puede especificar el nivel de acceso de una estructura mediante la [pública](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), o [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave, o puede dejar de forma predeterminada `Public`.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  <span data-ttu-id="7bf7b-114">Agregar elementos al cuerpo de la estructura.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="7bf7b-115">Una estructura debe tener al menos un elemento.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-115">A structure must have at least one element.</span></span> <span data-ttu-id="7bf7b-116">Debe declarar todos los elementos y especificar un nivel de acceso para él.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="7bf7b-117">Si usas el [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) sin palabras clave, valores predeterminados de la accesibilidad a `Public`.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="7bf7b-118">El `salary` campo en el ejemplo anterior es `Private`, lo que significa que no es accesible fuera de la estructura, incluso desde la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="7bf7b-119">Sin embargo, el `giveRaise` procedimiento es `Public`, por lo que se puede llamar desde fuera de la estructura.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="7bf7b-120">De forma similar, puede elevar la `salaryReviewTime` evento desde fuera de la estructura.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="7bf7b-121">Además de las variables, `Sub` procedimientos y eventos, también puede definir constantes, `Function` procedimientos y propiedades en una estructura.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="7bf7b-122">Puede designar como máximo una propiedad como el *propiedad predeterminada*, siempre que tarda al menos un argumento.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="7bf7b-123">Puede controlar un evento con un [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7bf7b-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="7bf7b-124">Para obtener más información, vea [Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span><span class="sxs-lookup"><span data-stu-id="7bf7b-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf7b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bf7b-125">See also</span></span>
- [<span data-ttu-id="7bf7b-126">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7bf7b-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="7bf7b-127">Tipos de datos básicos</span><span class="sxs-lookup"><span data-stu-id="7bf7b-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="7bf7b-128">Tipos de datos compuestos</span><span class="sxs-lookup"><span data-stu-id="7bf7b-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="7bf7b-129">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="7bf7b-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="7bf7b-130">Estructuras</span><span class="sxs-lookup"><span data-stu-id="7bf7b-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="7bf7b-131">Solución de problemas de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7bf7b-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="7bf7b-132">Variables de estructura</span><span class="sxs-lookup"><span data-stu-id="7bf7b-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="7bf7b-133">Estructuras y otros elementos de programación</span><span class="sxs-lookup"><span data-stu-id="7bf7b-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="7bf7b-134">Estructuras y clases</span><span class="sxs-lookup"><span data-stu-id="7bf7b-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="7bf7b-135">Tipo de datos definido por el usuario</span><span class="sxs-lookup"><span data-stu-id="7bf7b-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
