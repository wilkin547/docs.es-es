---
title: "No se puede hacer referencia a un miembro de instancia de una clase desde un método compartido o un inicializador de método compartido sin una instancia explícita de la clase"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6a15d36c0b3a4d6b1657d583de0dc61621da960d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="4879d-102">No se puede hacer referencia a un miembro de instancia de una clase desde un método compartido o un inicializador de método compartido sin una instancia explícita de la clase</span><span class="sxs-lookup"><span data-stu-id="4879d-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="4879d-103">Ha intentado hacer referencia a un miembro no compartido de una clase desde dentro de un procedimiento compartido.</span><span class="sxs-lookup"><span data-stu-id="4879d-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="4879d-104">En el ejemplo siguiente se muestra esta situación.</span><span class="sxs-lookup"><span data-stu-id="4879d-104">The following example demonstrates such a situation.</span></span>  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="4879d-105">En el ejemplo anterior, la instrucción de asignación `x = 10` genera este mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="4879d-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="4879d-106">Esto es porque un procedimiento compartido está intentando tener acceso a una variable de instancia.</span><span class="sxs-lookup"><span data-stu-id="4879d-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="4879d-107">La variable `x` es un miembro de instancia porque no está declarado como [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="4879d-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="4879d-108">Cada instancia de clase `sample` contiene su propia variable individual `x`.</span><span class="sxs-lookup"><span data-stu-id="4879d-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="4879d-109">Cuando una instancia establece o cambia el valor de `x`, no afecta al valor de `x` en cualquier otra instancia.</span><span class="sxs-lookup"><span data-stu-id="4879d-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="4879d-110">Sin embargo, el procedimiento `setX` es `Shared` entre todas las instancias de clase `sample`.</span><span class="sxs-lookup"><span data-stu-id="4879d-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="4879d-111">Esto significa no está asociado a ninguna instancia de la clase, sino que funciona independientemente de las instancias individuales.</span><span class="sxs-lookup"><span data-stu-id="4879d-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="4879d-112">Porque no tiene ninguna conexión con una instancia concreta, `setX` no se puede obtener acceso a una variable de instancia.</span><span class="sxs-lookup"><span data-stu-id="4879d-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="4879d-113">Debe funcionar solo en `Shared` variables.</span><span class="sxs-lookup"><span data-stu-id="4879d-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="4879d-114">Cuando `setX` establece o cambia el valor de una variable compartida, que el nuevo valor está disponible para todas las instancias de la clase.</span><span class="sxs-lookup"><span data-stu-id="4879d-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="4879d-115">**Id. de error:** BC30369</span><span class="sxs-lookup"><span data-stu-id="4879d-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4879d-116">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4879d-116">To correct this error</span></span>  
  
1.  <span data-ttu-id="4879d-117">Decida si desea que el miembro se comparten entre todas las instancias de la clase, o sea individual para cada instancia.</span><span class="sxs-lookup"><span data-stu-id="4879d-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2.  <span data-ttu-id="4879d-118">Si desea que una sola copia del miembro que se comparten entre todas las instancias, agregue el `Shared` palabra clave para la declaración del miembro.</span><span class="sxs-lookup"><span data-stu-id="4879d-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="4879d-119">Conservar el `Shared` palabra clave en la declaración de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4879d-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3.  <span data-ttu-id="4879d-120">Si desea que cada instancia tiene su propia copia individual del miembro, no especifique `Shared` para la declaración del miembro.</span><span class="sxs-lookup"><span data-stu-id="4879d-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="4879d-121">Quitar el `Shared` palabra clave de la declaración de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4879d-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4879d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4879d-122">See Also</span></span>  
 [<span data-ttu-id="4879d-123">Shared</span><span class="sxs-lookup"><span data-stu-id="4879d-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
