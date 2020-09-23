---
title: Procedimiento para controlar la disponibilidad de una variable
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
ms.openlocfilehash: e6173a0eaa0bf84abb1979711c6df932533c5ce9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086119"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="1f048-102">Cómo: Controlar la disponibilidad de una variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f048-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>

<span data-ttu-id="1f048-103">Puede controlar la disponibilidad de una variable especificando su *nivel de acceso*.</span><span class="sxs-lookup"><span data-stu-id="1f048-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="1f048-104">El nivel de acceso determina qué código tiene permiso para leer o escribir en la variable.</span><span class="sxs-lookup"><span data-stu-id="1f048-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
- <span data-ttu-id="1f048-105">*Las variables de miembro* (definidas en el nivel de módulo y fuera de cualquier procedimiento) tienen como valor predeterminado el acceso público, lo que significa que cualquier código que pueda verlas puede tener acceso a ellas.</span><span class="sxs-lookup"><span data-stu-id="1f048-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="1f048-106">Puede cambiar esto especificando un modificador de acceso.</span><span class="sxs-lookup"><span data-stu-id="1f048-106">You can change this by specifying an access modifier.</span></span>  
  
- <span data-ttu-id="1f048-107">*Las variables locales* (definidas dentro de un procedimiento) tienen un acceso público nominal, aunque solo el código de su procedimiento puede tener acceso a ellas.</span><span class="sxs-lookup"><span data-stu-id="1f048-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="1f048-108">No se puede cambiar el nivel de acceso de una variable local, pero se puede cambiar el nivel de acceso del procedimiento que lo contiene.</span><span class="sxs-lookup"><span data-stu-id="1f048-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="1f048-109">Para obtener más información, consulte [niveles de acceso en Visual Basic](access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1f048-109">For more information, see [Access levels in Visual Basic](access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="1f048-110">Acceso privado y público</span><span class="sxs-lookup"><span data-stu-id="1f048-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="1f048-111">Para hacer que una variable sea accesible solo desde dentro de su módulo, clase o estructura</span><span class="sxs-lookup"><span data-stu-id="1f048-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="1f048-112">Coloque la [instrucción Dim](../../../language-reference/statements/dim-statement.md) para la variable dentro del módulo, la clase o la estructura, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1f048-112">Place the [Dim Statement](../../../language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="1f048-113">Incluya la palabra clave [Private](../../../language-reference/modifiers/private.md) en la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1f048-113">Include the [Private](../../../language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="1f048-114">Puede leer o escribir en la variable desde cualquier lugar dentro del módulo, clase o estructura, pero no desde fuera de ella.</span><span class="sxs-lookup"><span data-stu-id="1f048-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="1f048-115">Para hacer que una variable sea accesible desde cualquier código que pueda verla</span><span class="sxs-lookup"><span data-stu-id="1f048-115">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="1f048-116">En el caso de una variable miembro, coloque la `Dim` instrucción para la variable dentro de un módulo, clase o estructura, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1f048-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="1f048-117">Incluya la palabra clave [Public](../../../language-reference/modifiers/public.md) en la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1f048-117">Include the [Public](../../../language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="1f048-118">Puede leer o escribir en la variable desde cualquier código que interopere con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1f048-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="1f048-119">o bien</span><span class="sxs-lookup"><span data-stu-id="1f048-119">-or-</span></span>  
  
1. <span data-ttu-id="1f048-120">En el caso de una variable local, coloque la `Dim` instrucción para la variable dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1f048-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="1f048-121">No incluya la `Public` palabra clave en la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1f048-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="1f048-122">Puede leer o escribir en la variable desde cualquier lugar dentro del procedimiento, pero no desde fuera de ella.</span><span class="sxs-lookup"><span data-stu-id="1f048-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="1f048-123">Acceso protegido y de confianza</span><span class="sxs-lookup"><span data-stu-id="1f048-123">Protected and Friend Access</span></span>  

 <span data-ttu-id="1f048-124">Puede limitar el nivel de acceso de una variable a su clase y las clases derivadas, o a su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1f048-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="1f048-125">También puede especificar la Unión de estas limitaciones, lo que permite el acceso desde el código de cualquier clase derivada o en cualquier otro lugar del mismo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1f048-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="1f048-126">Esta Unión se especifica combinando las `Protected` `Friend` palabras clave y en la misma declaración.</span><span class="sxs-lookup"><span data-stu-id="1f048-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="1f048-127">Para hacer que una variable sea accesible solo desde dentro de su clase y las clases derivadas</span><span class="sxs-lookup"><span data-stu-id="1f048-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="1f048-128">Coloque la `Dim` instrucción para la variable dentro de una clase, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1f048-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="1f048-129">Incluya la palabra clave [Protected](../../../language-reference/modifiers/protected.md) en la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1f048-129">Include the [Protected](../../../language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="1f048-130">Puede leer o escribir en la variable desde cualquier parte dentro de la clase, así como desde cualquier clase derivada de ella, pero no desde fuera de cualquier clase de la cadena de derivación.</span><span class="sxs-lookup"><span data-stu-id="1f048-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="1f048-131">Para hacer que una variable sea accesible solo desde dentro del mismo ensamblado</span><span class="sxs-lookup"><span data-stu-id="1f048-131">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="1f048-132">Coloque la `Dim` instrucción para la variable dentro de un módulo, clase o estructura, pero fuera de cualquier procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1f048-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="1f048-133">Incluya la palabra clave [Friend](../../../language-reference/modifiers/friend.md) en la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="1f048-133">Include the [Friend](../../../language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="1f048-134">Puede leer o escribir en la variable desde cualquier lugar dentro del módulo, clase o estructura, así como desde cualquier código del mismo ensamblado, pero no desde fuera del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1f048-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f048-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f048-135">Example</span></span>  

 <span data-ttu-id="1f048-136">En el ejemplo siguiente se muestran las declaraciones de variables con `Public` `Protected` `Friend` los niveles de acceso,,, `Protected Friend` y `Private` .</span><span class="sxs-lookup"><span data-stu-id="1f048-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="1f048-137">Tenga en cuenta que cuando la `Dim` instrucción especifica un nivel de acceso, no es necesario incluir la `Dim` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1f048-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="1f048-138">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1f048-138">.NET Framework Security</span></span>  

 <span data-ttu-id="1f048-139">Cuanto más restrictiva sea el nivel de acceso de una variable, menor será la probabilidad de que el código malintencionado pueda usarse de forma inadecuada.</span><span class="sxs-lookup"><span data-stu-id="1f048-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f048-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f048-140">See also</span></span>

- [<span data-ttu-id="1f048-141">Niveles de acceso en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1f048-141">Access levels in Visual Basic</span></span>](access-levels.md)
- [<span data-ttu-id="1f048-142">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="1f048-142">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="1f048-143">Pública</span><span class="sxs-lookup"><span data-stu-id="1f048-143">Public</span></span>](../../../language-reference/modifiers/public.md)
- [<span data-ttu-id="1f048-144">Contra</span><span class="sxs-lookup"><span data-stu-id="1f048-144">Protected</span></span>](../../../language-reference/modifiers/protected.md)
- [<span data-ttu-id="1f048-145">Friend</span><span class="sxs-lookup"><span data-stu-id="1f048-145">Friend</span></span>](../../../language-reference/modifiers/friend.md)
- [<span data-ttu-id="1f048-146">Privado</span><span class="sxs-lookup"><span data-stu-id="1f048-146">Private</span></span>](../../../language-reference/modifiers/private.md)
