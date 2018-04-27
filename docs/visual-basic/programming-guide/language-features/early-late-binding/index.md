---
title: Enlace en tiempo de compilación y en tiempo de ejecución (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- early binding [Visual Basic]
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding [Visual Basic], Visual Basic compiler
- binding [Visual Basic], late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding [Visual Basic]
- late binding [Visual Basic], Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10ecc965fb6d728454b3af33a6e93b2d7dbc327d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="early-and-late-binding-visual-basic"></a><span data-ttu-id="3af2e-102">Enlace en tiempo de compilación y en tiempo de ejecución (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3af2e-102">Early and Late Binding (Visual Basic)</span></span>
<span data-ttu-id="3af2e-103">El compilador de Visual Basic ejecuta un proceso denominado `binding` cuando se asigna un objeto a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="3af2e-103">The Visual Basic compiler performs a process called `binding` when an object is assigned to an object variable.</span></span> <span data-ttu-id="3af2e-104">Un objeto se *enlaza de manera anticipada* cuando se asigna a una variable que se declara de un tipo de objeto específico.</span><span class="sxs-lookup"><span data-stu-id="3af2e-104">An object is *early bound* when it is assigned to a variable declared to be of a specific object type.</span></span> <span data-ttu-id="3af2e-105">Los objetos enlazados de manera anticipada permiten al compilador asignar memoria y realizar otras optimizaciones antes de que se ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3af2e-105">Early bound objects allow the compiler to allocate memory and perform other optimizations before an application executes.</span></span> <span data-ttu-id="3af2e-106">Por ejemplo, el fragmento de código siguiente declara que una variable es de tipo <xref:System.IO.FileStream>:</span><span class="sxs-lookup"><span data-stu-id="3af2e-106">For example, the following code fragment declares a variable to be of type <xref:System.IO.FileStream>:</span></span>  
  
 [!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]  
  
 <span data-ttu-id="3af2e-107">Como <xref:System.IO.FileStream> es un tipo de objeto específico, la instancia asignada a `FS` se enlaza de manera anticipada.</span><span class="sxs-lookup"><span data-stu-id="3af2e-107">Because <xref:System.IO.FileStream> is a specific object type, the instance assigned to `FS` is early bound.</span></span>  
  
 <span data-ttu-id="3af2e-108">Por el contrario, un objeto se *enlaza en tiempo de ejecución* cuando se asigna a una variable que se declara como variable de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="3af2e-108">By contrast, an object is *late bound* when it is assigned to a variable declared to be of type `Object`.</span></span> <span data-ttu-id="3af2e-109">Los objetos de este tipo pueden contener referencias a cualquier objeto, pero carecen de muchas de las ventajas de los objetos con enlaces anticipados.</span><span class="sxs-lookup"><span data-stu-id="3af2e-109">Objects of this type can hold references to any object, but lack many of the advantages of early-bound objects.</span></span> <span data-ttu-id="3af2e-110">Por ejemplo, el fragmento de código siguiente declara una variable de objeto para contener un objeto devuelto por la función `CreateObject`:</span><span class="sxs-lookup"><span data-stu-id="3af2e-110">For example, the following code fragment declares an object variable to hold an object returned by the `CreateObject` function:</span></span>  
  
 [!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]  
  
## <a name="advantages-of-early-binding"></a><span data-ttu-id="3af2e-111">Ventajas del enlace anticipado</span><span class="sxs-lookup"><span data-stu-id="3af2e-111">Advantages of Early Binding</span></span>  
 <span data-ttu-id="3af2e-112">Debe utilizar objetos con enlace anticipado siempre que sea posible, ya que permiten al compilador realizar importantes optimizaciones que producen aplicaciones más eficientes.</span><span class="sxs-lookup"><span data-stu-id="3af2e-112">You should use early-bound objects whenever possible, because they allow the compiler to make important optimizations that yield more efficient applications.</span></span> <span data-ttu-id="3af2e-113">Los objetos con enlace anticipado son considerablemente más rápidos que los objetos con enlace en tiempo de ejecución y permiten que el código sea más fácil de leer y mantener, ya que declaran exactamente qué clase de objetos se están utilizando.</span><span class="sxs-lookup"><span data-stu-id="3af2e-113">Early-bound objects are significantly faster than late-bound objects and make your code easier to read and maintain by stating exactly what kind of objects are being used.</span></span> <span data-ttu-id="3af2e-114">Otra ventaja del enlace anticipado es que habilita características útiles como la finalización automática de código y la Ayuda dinámica, porque el entorno de desarrollo integrado (IDE) de [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] puede determinar exactamente con qué tipo de objeto está trabajando mientras se edita el código.</span><span class="sxs-lookup"><span data-stu-id="3af2e-114">Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code.</span></span> <span data-ttu-id="3af2e-115">El enlace anticipado reduce el número y la gravedad de los errores en tiempo de ejecución porque permite que el compilador notifique errores cuando se compila un programa.</span><span class="sxs-lookup"><span data-stu-id="3af2e-115">Early binding reduces the number and severity of run-time errors because it allows the compiler to report errors when a program is compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3af2e-116">El enlace en tiempo de ejecución solo puede utilizarse para acceder a miembros de tipo declarados como `Public`.</span><span class="sxs-lookup"><span data-stu-id="3af2e-116">Late binding can only be used to access type members that are declared as `Public`.</span></span> <span data-ttu-id="3af2e-117">El acceso a miembros declarados como `Friend` o `Protected Friend` produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3af2e-117">Accessing members declared as `Friend` or `Protected Friend` results in a run-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af2e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3af2e-118">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>  
 [<span data-ttu-id="3af2e-119">Duración de los objetos: cómo se crean y destruyen</span><span class="sxs-lookup"><span data-stu-id="3af2e-119">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [<span data-ttu-id="3af2e-120">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="3af2e-120">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
