---
description: 'Más información sobre: Implements (instrucción)'
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
ms.openlocfilehash: aa53d1f3b4ba9d9111f5ffb09198a11511f8d9e9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768992"
---
# <a name="implements-statement"></a><span data-ttu-id="b9b16-103">Implements (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="b9b16-103">Implements Statement</span></span>

<span data-ttu-id="b9b16-104">Especifica una o más interfaces, o miembros de interfaz, que se deben implementar en la definición de clase o estructura en la que aparece.</span><span class="sxs-lookup"><span data-stu-id="b9b16-104">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b16-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9b16-105">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="b9b16-106">Partes</span><span class="sxs-lookup"><span data-stu-id="b9b16-106">Parts</span></span>  

 `interfacename`  
 <span data-ttu-id="b9b16-107">Necesario.</span><span class="sxs-lookup"><span data-stu-id="b9b16-107">Required.</span></span> <span data-ttu-id="b9b16-108">Interfaz cuyas propiedades, procedimientos y eventos van a ser implementados por los miembros correspondientes de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="b9b16-108">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="b9b16-109">Necesario.</span><span class="sxs-lookup"><span data-stu-id="b9b16-109">Required.</span></span> <span data-ttu-id="b9b16-110">Miembro de una interfaz que se está implementando.</span><span class="sxs-lookup"><span data-stu-id="b9b16-110">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9b16-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b9b16-111">Remarks</span></span>  

 <span data-ttu-id="b9b16-112">Una interfaz es una colección de prototipos que representan los miembros (propiedades, procedimientos y eventos) que la interfaz encapsula.</span><span class="sxs-lookup"><span data-stu-id="b9b16-112">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="b9b16-113">Las interfaces contienen solo las declaraciones de los miembros; las clases y estructuras implementan estos miembros.</span><span class="sxs-lookup"><span data-stu-id="b9b16-113">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="b9b16-114">Para obtener más información, vea [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="b9b16-114">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="b9b16-115">La `Implements` instrucción debe seguir inmediatamente a `Class` la `Structure` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="b9b16-115">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="b9b16-116">Al implementar una interfaz, debe implementar todos los miembros declarados en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b9b16-116">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="b9b16-117">Omitir cualquier miembro se considera un error de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="b9b16-117">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="b9b16-118">Para implementar un miembro individual, se especifica la palabra clave [Implements](implements-clause.md) (que es independiente de la `Implements` instrucción) cuando se declara el miembro en la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="b9b16-118">To implement an individual member, you specify the [Implements](implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="b9b16-119">Para obtener más información, vea [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="b9b16-119">For more information, see [Interfaces](../../programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="b9b16-120">Las clases pueden utilizar implementaciones [privadas](../modifiers/private.md) de propiedades y procedimientos, pero solo se puede tener acceso a estos miembros si se convierte una instancia de la clase de implementación en una variable declarada como del tipo de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b9b16-120">Classes can use [Private](../modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9b16-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9b16-121">Example</span></span>  

 <span data-ttu-id="b9b16-122">En el ejemplo siguiente se muestra cómo utilizar la `Implements` instrucción para implementar miembros de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="b9b16-122">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="b9b16-123">Define una interfaz denominada `ICustomerInfo` con un evento, una propiedad y un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b9b16-123">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="b9b16-124">La clase `customerInfo` implementa todos los miembros definidos en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="b9b16-124">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="b9b16-125">Tenga en cuenta que la clase `customerInfo` utiliza la `Implements` instrucción en una línea de código fuente independiente para indicar que la clase implementa todos los miembros de la `ICustomerInfo` interfaz.</span><span class="sxs-lookup"><span data-stu-id="b9b16-125">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="b9b16-126">Después, cada miembro de la clase usa la `Implements` palabra clave como parte de su declaración de miembro para indicar que implementa ese miembro de interfaz.</span><span class="sxs-lookup"><span data-stu-id="b9b16-126">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9b16-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9b16-127">Example</span></span>  

 <span data-ttu-id="b9b16-128">Los dos procedimientos siguientes muestran cómo podría usar la interfaz implementada en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="b9b16-128">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="b9b16-129">Para probar la implementación, agregue estos procedimientos al proyecto y llame al `testImplements` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="b9b16-129">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="b9b16-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9b16-130">See also</span></span>

- [<span data-ttu-id="b9b16-131">Implementaciones</span><span class="sxs-lookup"><span data-stu-id="b9b16-131">Implements</span></span>](implements-clause.md)
- [<span data-ttu-id="b9b16-132">Instrucción Interface</span><span class="sxs-lookup"><span data-stu-id="b9b16-132">Interface Statement</span></span>](interface-statement.md)
- [<span data-ttu-id="b9b16-133">Interfaces</span><span class="sxs-lookup"><span data-stu-id="b9b16-133">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
