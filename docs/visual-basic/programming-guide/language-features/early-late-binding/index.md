---
description: 'Más información sobre: enlace anticipado y en tiempo de ejecución (Visual Basic)'
title: Enlace en tiempo de compilación y en tiempo de ejecución
ms.date: 07/20/2015
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
ms.openlocfilehash: 1cdffe70035630ec56de04c54d7861283e1b5599
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475635"
---
# <a name="early-and-late-binding-visual-basic"></a><span data-ttu-id="615ad-103">Enlace en tiempo de compilación y en tiempo de ejecución (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="615ad-103">Early and Late Binding (Visual Basic)</span></span>

<span data-ttu-id="615ad-104">El compilador de Visual Basic realiza un proceso al `binding` que se llama cuando se asigna un objeto a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="615ad-104">The Visual Basic compiler performs a process called `binding` when an object is assigned to an object variable.</span></span> <span data-ttu-id="615ad-105">Un objeto se *enlaza de manera anticipada* cuando se asigna a una variable que se declara de un tipo de objeto específico.</span><span class="sxs-lookup"><span data-stu-id="615ad-105">An object is *early bound* when it is assigned to a variable declared to be of a specific object type.</span></span> <span data-ttu-id="615ad-106">Los objetos enlazados de manera anticipada permiten al compilador asignar memoria y realizar otras optimizaciones antes de que se ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="615ad-106">Early bound objects allow the compiler to allocate memory and perform other optimizations before an application executes.</span></span> <span data-ttu-id="615ad-107">Por ejemplo, el fragmento de código siguiente declara que una variable es de tipo <xref:System.IO.FileStream>:</span><span class="sxs-lookup"><span data-stu-id="615ad-107">For example, the following code fragment declares a variable to be of type <xref:System.IO.FileStream>:</span></span>  
  
 [!code-vb[VbVbalrOOP#90](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#90)]  
  
 <span data-ttu-id="615ad-108">Como <xref:System.IO.FileStream> es un tipo de objeto específico, la instancia asignada a `FS` se enlaza de manera anticipada.</span><span class="sxs-lookup"><span data-stu-id="615ad-108">Because <xref:System.IO.FileStream> is a specific object type, the instance assigned to `FS` is early bound.</span></span>  
  
 <span data-ttu-id="615ad-109">Por el contrario, un objeto se *enlaza en tiempo de ejecución* cuando se asigna a una variable que se declara como variable de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="615ad-109">By contrast, an object is *late bound* when it is assigned to a variable declared to be of type `Object`.</span></span> <span data-ttu-id="615ad-110">Los objetos de este tipo pueden contener referencias a cualquier objeto, pero carecen de muchas de las ventajas de los objetos con enlaces anticipados.</span><span class="sxs-lookup"><span data-stu-id="615ad-110">Objects of this type can hold references to any object, but lack many of the advantages of early-bound objects.</span></span> <span data-ttu-id="615ad-111">Por ejemplo, el fragmento de código siguiente declara una variable de objeto para contener un objeto devuelto por la función `CreateObject`:</span><span class="sxs-lookup"><span data-stu-id="615ad-111">For example, the following code fragment declares an object variable to hold an object returned by the `CreateObject` function:</span></span>  
  
 [!code-vb[VbVbalrOOP#91](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/LateBinding.vb#91)]  
  
## <a name="advantages-of-early-binding"></a><span data-ttu-id="615ad-112">Ventajas del enlace anticipado</span><span class="sxs-lookup"><span data-stu-id="615ad-112">Advantages of Early Binding</span></span>  

 <span data-ttu-id="615ad-113">Debe utilizar objetos con enlace anticipado siempre que sea posible, ya que permiten al compilador realizar importantes optimizaciones que producen aplicaciones más eficientes.</span><span class="sxs-lookup"><span data-stu-id="615ad-113">You should use early-bound objects whenever possible, because they allow the compiler to make important optimizations that yield more efficient applications.</span></span> <span data-ttu-id="615ad-114">Los objetos con enlace anticipado son considerablemente más rápidos que los objetos con enlace en tiempo de ejecución y permiten que el código sea más fácil de leer y mantener, ya que declaran exactamente qué clase de objetos se están utilizando.</span><span class="sxs-lookup"><span data-stu-id="615ad-114">Early-bound objects are significantly faster than late-bound objects and make your code easier to read and maintain by stating exactly what kind of objects are being used.</span></span> <span data-ttu-id="615ad-115">Otra ventaja del enlace en tiempo de compilación es que permite características útiles como la finalización automática de código y la ayuda dinámica, ya que el entorno de desarrollo integrado (IDE) de Visual Studio puede determinar exactamente el tipo de objeto con el que está trabajando mientras edita el código.</span><span class="sxs-lookup"><span data-stu-id="615ad-115">Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the Visual Studio integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code.</span></span> <span data-ttu-id="615ad-116">El enlace anticipado reduce el número y la gravedad de los errores en tiempo de ejecución porque permite que el compilador notifique errores cuando se compila un programa.</span><span class="sxs-lookup"><span data-stu-id="615ad-116">Early binding reduces the number and severity of run-time errors because it allows the compiler to report errors when a program is compiled.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="615ad-117">El enlace en tiempo de ejecución solo puede utilizarse para acceder a miembros de tipo declarados como `Public`.</span><span class="sxs-lookup"><span data-stu-id="615ad-117">Late binding can only be used to access type members that are declared as `Public`.</span></span> <span data-ttu-id="615ad-118">El acceso a miembros declarados como `Friend` o `Protected Friend` produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="615ad-118">Accessing members declared as `Friend` or `Protected Friend` results in a run-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="615ad-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="615ad-119">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>
- [<span data-ttu-id="615ad-120">Duración de los objetos: cómo se crean y destruyen</span><span class="sxs-lookup"><span data-stu-id="615ad-120">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [<span data-ttu-id="615ad-121">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="615ad-121">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
