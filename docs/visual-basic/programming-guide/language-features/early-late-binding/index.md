---
title: "Enlace en tiempo de compilación y en tiempo de ejecución (Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- early binding
- objects [Visual Basic], late-bound
- objects [Visual Basic], early-bound
- objects [Visual Basic], late bound
- early binding, Visual Basic compiler
- binding, late and early
- objects [Visual Basic], early bound
- Visual Basic compiler, early and late binding
- late binding
- late binding, Visual Basic compiler
ms.assetid: d6ff7f1e-b94f-4205-ab8d-5cfa91758724
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 66a34580417fb8b4a814b237ec36ffe700b1b30a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="early-and-late-binding-visual-basic"></a><span data-ttu-id="e9c09-102">Enlace en tiempo de compilación y en tiempo de ejecución (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9c09-102">Early and Late Binding (Visual Basic)</span></span>
<span data-ttu-id="e9c09-103">El compilador [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] lleva a cabo un proceso denominado `binding` cuando se asigna un objeto a una variable de objeto.</span><span class="sxs-lookup"><span data-stu-id="e9c09-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler performs a process called `binding` when an object is assigned to an object variable.</span></span> <span data-ttu-id="e9c09-104">Un objeto se *enlaza de manera anticipada* cuando se asigna a una variable que se declara de un tipo de objeto específico.</span><span class="sxs-lookup"><span data-stu-id="e9c09-104">An object is *early bound* when it is assigned to a variable declared to be of a specific object type.</span></span> <span data-ttu-id="e9c09-105">Los objetos enlazados de manera anticipada permiten al compilador asignar memoria y realizar otras optimizaciones antes de que se ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9c09-105">Early bound objects allow the compiler to allocate memory and perform other optimizations before an application executes.</span></span> <span data-ttu-id="e9c09-106">Por ejemplo, el fragmento de código siguiente declara que una variable es de tipo <xref:System.IO.FileStream>:</span><span class="sxs-lookup"><span data-stu-id="e9c09-106">For example, the following code fragment declares a variable to be of type <xref:System.IO.FileStream>:</span></span>  
  
 <span data-ttu-id="e9c09-107">[!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e9c09-107">[!code-vb[VbVbalrOOP#90](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_1.vb)]</span></span>  
  
 <span data-ttu-id="e9c09-108">Como <xref:System.IO.FileStream> es un tipo de objeto específico, la instancia asignada a `FS` se enlaza de manera anticipada.</span><span class="sxs-lookup"><span data-stu-id="e9c09-108">Because <xref:System.IO.FileStream> is a specific object type, the instance assigned to `FS` is early bound.</span></span>  
  
 <span data-ttu-id="e9c09-109">Por el contrario, un objeto se *enlaza en tiempo de ejecución* cuando se asigna a una variable que se declara como variable de tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="e9c09-109">By contrast, an object is *late bound* when it is assigned to a variable declared to be of type `Object`.</span></span> <span data-ttu-id="e9c09-110">Los objetos de este tipo pueden contener referencias a cualquier objeto, pero carecen de muchas de las ventajas de los objetos con enlaces anticipados.</span><span class="sxs-lookup"><span data-stu-id="e9c09-110">Objects of this type can hold references to any object, but lack many of the advantages of early-bound objects.</span></span> <span data-ttu-id="e9c09-111">Por ejemplo, el fragmento de código siguiente declara una variable de objeto para contener un objeto devuelto por la función `CreateObject`:</span><span class="sxs-lookup"><span data-stu-id="e9c09-111">For example, the following code fragment declares an object variable to hold an object returned by the `CreateObject` function:</span></span>  
  
 <span data-ttu-id="e9c09-112">[!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e9c09-112">[!code-vb[VbVbalrOOP#91](../../../../visual-basic/misc/codesnippet/VisualBasic/early-and-late-binding_2.vb)]</span></span>  
  
## <a name="advantages-of-early-binding"></a><span data-ttu-id="e9c09-113">Ventajas del enlace anticipado</span><span class="sxs-lookup"><span data-stu-id="e9c09-113">Advantages of Early Binding</span></span>  
 <span data-ttu-id="e9c09-114">Debe utilizar objetos con enlace anticipado siempre que sea posible, ya que permiten al compilador realizar importantes optimizaciones que producen aplicaciones más eficientes.</span><span class="sxs-lookup"><span data-stu-id="e9c09-114">You should use early-bound objects whenever possible, because they allow the compiler to make important optimizations that yield more efficient applications.</span></span> <span data-ttu-id="e9c09-115">Los objetos con enlace anticipado son considerablemente más rápidos que los objetos con enlace en tiempo de ejecución y permiten que el código sea más fácil de leer y mantener, ya que declaran exactamente qué clase de objetos se están utilizando.</span><span class="sxs-lookup"><span data-stu-id="e9c09-115">Early-bound objects are significantly faster than late-bound objects and make your code easier to read and maintain by stating exactly what kind of objects are being used.</span></span> <span data-ttu-id="e9c09-116">Otra ventaja del enlace anticipado es que habilita características útiles como la finalización automática de código y la Ayuda dinámica, porque el entorno de desarrollo integrado (IDE) de [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] puede determinar exactamente con qué tipo de objeto está trabajando mientras se edita el código.</span><span class="sxs-lookup"><span data-stu-id="e9c09-116">Another advantage to early binding is that it enables useful features such as automatic code completion and Dynamic Help because the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] integrated development environment (IDE) can determine exactly what type of object you are working with as you edit the code.</span></span> <span data-ttu-id="e9c09-117">El enlace anticipado reduce el número y la gravedad de los errores en tiempo de ejecución porque permite que el compilador notifique errores cuando se compila un programa.</span><span class="sxs-lookup"><span data-stu-id="e9c09-117">Early binding reduces the number and severity of run-time errors because it allows the compiler to report errors when a program is compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9c09-118">El enlace en tiempo de ejecución solo puede utilizarse para acceder a miembros de tipo declarados como `Public`.</span><span class="sxs-lookup"><span data-stu-id="e9c09-118">Late binding can only be used to access type members that are declared as `Public`.</span></span> <span data-ttu-id="e9c09-119">El acceso a miembros declarados como `Friend` o `Protected Friend` produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e9c09-119">Accessing members declared as `Friend` or `Protected Friend` results in a run-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c09-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9c09-120">See Also</span></span>  
 <span data-ttu-id="e9c09-121"><xref:Microsoft.VisualBasic.Interaction.CreateObject%2A></span><span class="sxs-lookup"><span data-stu-id="e9c09-121"><xref:Microsoft.VisualBasic.Interaction.CreateObject%2A></span></span>   
 <span data-ttu-id="e9c09-122">[Duración de los objetos: cómo se crean y destruyen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md) </span><span class="sxs-lookup"><span data-stu-id="e9c09-122">[Object Lifetime: How Objects Are Created and Destroyed](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md) </span></span>  
 [<span data-ttu-id="e9c09-123">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="e9c09-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)

