---
title: Filtrar Controlar la disponibilidad de una Variable (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: fb400b113e3f3305f5b724734b2bf9aa9425d03f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311531"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="f82f4-102">Filtrar Controlar la disponibilidad de una Variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f82f4-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="f82f4-103">Controlar la disponibilidad de una variable especificando su *nivel de acceso*.</span><span class="sxs-lookup"><span data-stu-id="f82f4-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="f82f4-104">El nivel de acceso determina qué código tiene permiso para leer o escribir en la variable.</span><span class="sxs-lookup"><span data-stu-id="f82f4-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
-   <span data-ttu-id="f82f4-105">*Variables de miembro* (definido en el nivel de módulo y fuera de cualquier procedimiento) predeterminado para el acceso público, lo que significa que cualquier código que pueda verlos puede tener acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="f82f4-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="f82f4-106">Puede cambiar esto especificando un modificador de acceso.</span><span class="sxs-lookup"><span data-stu-id="f82f4-106">You can change this by specifying an access modifier.</span></span>  
  
-   <span data-ttu-id="f82f4-107">*Las variables locales* (definido dentro de un procedimiento) nominalmente tienen acceso público, aunque sólo el código dentro de su procedimiento puede tener acceso a ellos.</span><span class="sxs-lookup"><span data-stu-id="f82f4-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="f82f4-108">No se puede cambiar el nivel de acceso de una variable local, pero puede cambiar el nivel de acceso del procedimiento que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="f82f4-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="f82f4-109">Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f82f4-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="f82f4-110">Acceso privado y público</span><span class="sxs-lookup"><span data-stu-id="f82f4-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="f82f4-111">Para hacer que una variable sea accesible únicamente desde dentro de su módulo, clase o estructura</span><span class="sxs-lookup"><span data-stu-id="f82f4-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="f82f4-112">Colocar el [instrucción Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) para la variable dentro del módulo, clase o estructura, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f82f4-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f82f4-113">Incluir el [privada](../../../../visual-basic/language-reference/modifiers/private.md) palabra clave en el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f82f4-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f82f4-114">Puede leer o escribir en la variable desde cualquier lugar dentro del módulo, clase o estructura, pero no desde fuera de él.</span><span class="sxs-lookup"><span data-stu-id="f82f4-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="f82f4-115">Para que una variable sea accesible desde cualquier código que pueda verla</span><span class="sxs-lookup"><span data-stu-id="f82f4-115">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="f82f4-116">Para una variable miembro, coloque el `Dim` instrucción para la variable dentro de un módulo, clase o estructura, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f82f4-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f82f4-117">Incluir el [pública](../../../../visual-basic/language-reference/modifiers/public.md) palabra clave en el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f82f4-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f82f4-118">Puede leer o escribir en la variable desde cualquier código que interactúa con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f82f4-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="f82f4-119">-o bien-</span><span class="sxs-lookup"><span data-stu-id="f82f4-119">-or-</span></span>  
  
1. <span data-ttu-id="f82f4-120">Para una variable local, coloque el `Dim` instrucción para la variable dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f82f4-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="f82f4-121">No incluya el `Public` palabra clave en el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f82f4-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f82f4-122">Puede leer o escribir en la variable desde cualquier lugar dentro del procedimiento, pero no desde fuera de él.</span><span class="sxs-lookup"><span data-stu-id="f82f4-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="f82f4-123">Protegido y el acceso de confianza</span><span class="sxs-lookup"><span data-stu-id="f82f4-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="f82f4-124">Puede limitar el nivel de acceso de una variable a su clase y las clases derivadas, o a su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f82f4-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="f82f4-125">También puede especificar la unión de estas limitaciones, que permite el acceso desde el código en cualquier clase derivada o en cualquier otro lugar en el mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f82f4-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="f82f4-126">Especifique esta unión combinando el `Protected` y `Friend` palabras clave en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="f82f4-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="f82f4-127">Para hacer que una variable sea accesible únicamente desde dentro de su clase y cualquiera de las clases derivadas</span><span class="sxs-lookup"><span data-stu-id="f82f4-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="f82f4-128">Colocar el `Dim` instrucción para la variable dentro de una clase, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f82f4-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f82f4-129">Incluir el [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) palabra clave en el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f82f4-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f82f4-130">Puede leer o escribir en la variable desde cualquier lugar dentro de la clase, así como desde cualquier clase derivada de él, pero no desde fuera de cualquier clase en la cadena de derivación.</span><span class="sxs-lookup"><span data-stu-id="f82f4-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="f82f4-131">Para hacer que una variable sea accesible únicamente desde dentro del mismo ensamblado</span><span class="sxs-lookup"><span data-stu-id="f82f4-131">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="f82f4-132">Colocar el `Dim` instrucción para la variable dentro de un módulo, clase o estructura, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="f82f4-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="f82f4-133">Incluir el [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) palabra clave en el `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="f82f4-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f82f4-134">Puede leer o escribir en la variable desde cualquier lugar dentro del módulo, clase o estructura, así como desde cualquier código en el mismo ensamblado, pero no desde fuera del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="f82f4-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f82f4-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f82f4-135">Example</span></span>  
 <span data-ttu-id="f82f4-136">El ejemplo siguiente muestra las declaraciones de variables con `Public`, `Protected`, `Friend`, `Protected Friend`, y `Private` niveles de acceso.</span><span class="sxs-lookup"><span data-stu-id="f82f4-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="f82f4-137">Tenga en cuenta que, cuando el `Dim` instrucción especifica un nivel de acceso, no es necesario incluir el `Dim` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="f82f4-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="f82f4-138">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f82f4-138">.NET Framework Security</span></span>  
 <span data-ttu-id="f82f4-139">Los permisos más restrictivos el nivel de acceso de una variable, cuantos menos las posibilidades de que código malintencionado puede hacer incorrecto usar del mismo.</span><span class="sxs-lookup"><span data-stu-id="f82f4-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f82f4-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="f82f4-140">See also</span></span>

- [<span data-ttu-id="f82f4-141">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f82f4-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="f82f4-142">Dim (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="f82f4-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="f82f4-143">Public</span><span class="sxs-lookup"><span data-stu-id="f82f4-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="f82f4-144">Protegido</span><span class="sxs-lookup"><span data-stu-id="f82f4-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="f82f4-145">Friend</span><span class="sxs-lookup"><span data-stu-id="f82f4-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="f82f4-146">Private</span><span class="sxs-lookup"><span data-stu-id="f82f4-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
