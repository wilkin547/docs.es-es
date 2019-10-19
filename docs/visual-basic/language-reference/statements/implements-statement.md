---
title: Implements (instrucción Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 865e99aa0e27591d10fde1465047a2e6bf183bbf
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581788"
---
# <a name="implements-statement"></a><span data-ttu-id="fb7b9-102">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="fb7b9-102">Implements Statement</span></span>
<span data-ttu-id="fb7b9-103">Especifica una o más interfaces, o miembros de interfaz, que se deben implementar en la definición de clase o estructura en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb7b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb7b9-104">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="fb7b9-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="fb7b9-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="fb7b9-106">Requerido.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-106">Required.</span></span> <span data-ttu-id="fb7b9-107">Interfaz cuyas propiedades, procedimientos y eventos van a ser implementados por los miembros correspondientes de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="fb7b9-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-108">Required.</span></span> <span data-ttu-id="fb7b9-109">Miembro de una interfaz que se está implementando.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb7b9-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb7b9-110">Remarks</span></span>  
 <span data-ttu-id="fb7b9-111">Una interfaz es una colección de prototipos que representan los miembros (propiedades, procedimientos y eventos) que la interfaz encapsula.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="fb7b9-112">Las interfaces contienen solo las declaraciones de los miembros; las clases y estructuras implementan estos miembros.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="fb7b9-113">Para obtener más información, vea [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b9-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="fb7b9-114">La instrucción `Implements` debe seguir inmediatamente a la instrucción `Class` o `Structure`.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="fb7b9-115">Al implementar una interfaz, debe implementar todos los miembros declarados en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="fb7b9-116">Omitir cualquier miembro se considera un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="fb7b9-117">Para implementar un miembro individual, se especifica la palabra clave [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) (que es independiente de la instrucción `Implements`) cuando se declara el miembro en la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="fb7b9-118">Para obtener más información, vea [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="fb7b9-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="fb7b9-119">Las clases pueden utilizar implementaciones [privadas](../../../visual-basic/language-reference/modifiers/private.md) de propiedades y procedimientos, pero solo se puede tener acceso a estos miembros si se convierte una instancia de la clase de implementación en una variable declarada como del tipo de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb7b9-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb7b9-120">Example</span></span>  
 <span data-ttu-id="fb7b9-121">En el ejemplo siguiente se muestra cómo utilizar la instrucción `Implements` para implementar miembros de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="fb7b9-122">Define una interfaz denominada `ICustomerInfo` con un evento, una propiedad y un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="fb7b9-123">La clase `customerInfo` implementa todos los miembros definidos en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="fb7b9-124">Tenga en cuenta que la clase `customerInfo` usa la instrucción `Implements` en una línea de código fuente independiente para indicar que la clase implementa todos los miembros de la interfaz `ICustomerInfo`.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="fb7b9-125">Después, cada miembro de la clase usa la palabra clave `Implements` como parte de su declaración de miembro para indicar que implementa ese miembro de interfaz.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb7b9-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb7b9-126">Example</span></span>  
 <span data-ttu-id="fb7b9-127">Los dos procedimientos siguientes muestran cómo podría usar la interfaz implementada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="fb7b9-128">Para probar la implementación, agregue estos procedimientos al proyecto y llame al procedimiento `testImplements`.</span><span class="sxs-lookup"><span data-stu-id="fb7b9-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="fb7b9-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb7b9-129">See also</span></span>

- [<span data-ttu-id="fb7b9-130">Implements</span><span class="sxs-lookup"><span data-stu-id="fb7b9-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)
- [<span data-ttu-id="fb7b9-131">Interface (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fb7b9-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="fb7b9-132">Interfaces</span><span class="sxs-lookup"><span data-stu-id="fb7b9-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
