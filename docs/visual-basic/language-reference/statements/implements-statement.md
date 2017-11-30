---
title: "Implements (Instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1103305ffbf5425d9a6a6a09695437968642710d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="implements-statement"></a><span data-ttu-id="26377-102">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="26377-102">Implements Statement</span></span>
<span data-ttu-id="26377-103">Especifica uno o más interfaces, o miembros de interfaz que deben implementarse en la clase o definición de la estructura en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="26377-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26377-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="26377-104">Syntax</span></span>  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="26377-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="26377-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="26377-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="26377-106">Required.</span></span> <span data-ttu-id="26377-107">Una interfaz cuyas propiedades, procedimientos y eventos deben implementarse por los miembros correspondientes de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="26377-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="26377-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="26377-108">Required.</span></span> <span data-ttu-id="26377-109">El miembro de interfaz que se está implementando.</span><span class="sxs-lookup"><span data-stu-id="26377-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26377-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="26377-110">Remarks</span></span>  
 <span data-ttu-id="26377-111">Una interfaz es una colección de prototipos que representan los miembros (propiedades, procedimientos y eventos) que encapsula la interfaz.</span><span class="sxs-lookup"><span data-stu-id="26377-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="26377-112">Interfaces sólo contienen las declaraciones de miembros; las clases y estructuras implementan a estos miembros.</span><span class="sxs-lookup"><span data-stu-id="26377-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="26377-113">Para obtener más información, vea [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="26377-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="26377-114">El `Implements` instrucción debe seguir inmediatamente el `Class` o `Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="26377-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="26377-115">Cuando se implementa una interfaz, debe implementar todos los miembros declarados en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="26377-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="26377-116">Si se omite a cualquier miembro se considera un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="26377-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="26377-117">Para implementar un miembro individual, especifique la [implementa](../../../visual-basic/language-reference/statements/implements-clause.md) palabra clave (que son independientes de la `Implements` instrucción) cuando se declara el miembro de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="26377-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="26377-118">Para obtener más información, vea [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="26377-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="26377-119">Pueden utilizar las clases [privada](../../../visual-basic/language-reference/modifiers/private.md) las implementaciones de propiedades y procedimientos, pero estos miembros son accesibles solo para convertir una instancia de la clase que se implementa en una variable se declara como del tipo de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="26377-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26377-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26377-120">Example</span></span>  
 <span data-ttu-id="26377-121">En el ejemplo siguiente se muestra cómo utilizar el `Implements` instrucción para implementar miembros de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="26377-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="26377-122">Define una interfaz denominada `ICustomerInfo` con un evento, una propiedad y un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="26377-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="26377-123">La clase `customerInfo` implementa todos los miembros definidos en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="26377-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 <span data-ttu-id="26377-124">Tenga en cuenta que la clase `customerInfo` utiliza la `Implements` instrucción en una línea de código fuente independiente para indicar que la clase implementa todos los miembros de la `ICustomerInfo` interfaz.</span><span class="sxs-lookup"><span data-stu-id="26377-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="26377-125">A continuación, todos los miembros de la clase usan el `Implements` palabra clave como parte de su declaración de miembro para indicar que implementa ese miembro de interfaz.</span><span class="sxs-lookup"><span data-stu-id="26377-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26377-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="26377-126">Example</span></span>  
 <span data-ttu-id="26377-127">Los dos procedimientos siguientes muestran cómo puede usar la interfaz implementada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="26377-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="26377-128">Para probar la implementación, agregue estos procedimientos en el proyecto y llame a la `testImplements` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="26377-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="26377-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="26377-129">See Also</span></span>  
 [<span data-ttu-id="26377-130">Implements</span><span class="sxs-lookup"><span data-stu-id="26377-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [<span data-ttu-id="26377-131">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="26377-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="26377-132">Interfaces</span><span class="sxs-lookup"><span data-stu-id="26377-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
