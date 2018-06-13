---
title: Implements (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 5afc7e4e3a03dfab1288e50e65e5076bdd438f7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604216"
---
# <a name="implements-statement"></a><span data-ttu-id="8308d-102">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="8308d-102">Implements Statement</span></span>
<span data-ttu-id="8308d-103">Especifica uno o más interfaces, o miembros de interfaz que deben implementarse en la clase o definición de la estructura en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="8308d-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8308d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8308d-104">Syntax</span></span>  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="8308d-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="8308d-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="8308d-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="8308d-106">Required.</span></span> <span data-ttu-id="8308d-107">Una interfaz cuyas propiedades, procedimientos y eventos deben implementarse por los miembros correspondientes de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="8308d-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="8308d-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="8308d-108">Required.</span></span> <span data-ttu-id="8308d-109">El miembro de interfaz que se está implementando.</span><span class="sxs-lookup"><span data-stu-id="8308d-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8308d-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8308d-110">Remarks</span></span>  
 <span data-ttu-id="8308d-111">Una interfaz es una colección de prototipos que representan los miembros (propiedades, procedimientos y eventos) que encapsula la interfaz.</span><span class="sxs-lookup"><span data-stu-id="8308d-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="8308d-112">Interfaces sólo contienen las declaraciones de miembros; las clases y estructuras implementan a estos miembros.</span><span class="sxs-lookup"><span data-stu-id="8308d-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="8308d-113">Para obtener más información, vea [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="8308d-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="8308d-114">El `Implements` instrucción debe seguir inmediatamente el `Class` o `Structure` instrucción.</span><span class="sxs-lookup"><span data-stu-id="8308d-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="8308d-115">Cuando se implementa una interfaz, debe implementar todos los miembros declarados en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="8308d-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="8308d-116">Si se omite a cualquier miembro se considera un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="8308d-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="8308d-117">Para implementar un miembro individual, especifique la [implementa](../../../visual-basic/language-reference/statements/implements-clause.md) palabra clave (que son independientes de la `Implements` instrucción) cuando se declara el miembro de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="8308d-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="8308d-118">Para obtener más información, vea [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="8308d-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="8308d-119">Pueden utilizar las clases [privada](../../../visual-basic/language-reference/modifiers/private.md) las implementaciones de propiedades y procedimientos, pero estos miembros son accesibles solo para convertir una instancia de la clase que se implementa en una variable se declara como del tipo de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="8308d-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8308d-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8308d-120">Example</span></span>  
 <span data-ttu-id="8308d-121">En el ejemplo siguiente se muestra cómo utilizar el `Implements` instrucción para implementar miembros de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="8308d-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="8308d-122">Define una interfaz denominada `ICustomerInfo` con un evento, una propiedad y un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8308d-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="8308d-123">La clase `customerInfo` implementa todos los miembros definidos en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="8308d-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 <span data-ttu-id="8308d-124">Tenga en cuenta que la clase `customerInfo` utiliza la `Implements` instrucción en una línea de código fuente independiente para indicar que la clase implementa todos los miembros de la `ICustomerInfo` interfaz.</span><span class="sxs-lookup"><span data-stu-id="8308d-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="8308d-125">A continuación, todos los miembros de la clase usan el `Implements` palabra clave como parte de su declaración de miembro para indicar que implementa ese miembro de interfaz.</span><span class="sxs-lookup"><span data-stu-id="8308d-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8308d-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8308d-126">Example</span></span>  
 <span data-ttu-id="8308d-127">Los dos procedimientos siguientes muestran cómo puede usar la interfaz implementada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="8308d-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="8308d-128">Para probar la implementación, agregue estos procedimientos en el proyecto y llame a la `testImplements` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8308d-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8308d-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="8308d-129">See Also</span></span>  
 [<span data-ttu-id="8308d-130">Implements</span><span class="sxs-lookup"><span data-stu-id="8308d-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [<span data-ttu-id="8308d-131">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8308d-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="8308d-132">Interfaces</span><span class="sxs-lookup"><span data-stu-id="8308d-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
