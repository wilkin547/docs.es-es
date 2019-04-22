---
title: Me, My, MyBase y MyClass en Visual Basic
ms.date: 07/20/2015
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
ms.openlocfilehash: a8df6e48fd5bce9bb28d8aef7e031f36741ad0ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813397"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="85688-102">Me, My, MyBase y MyClass en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="85688-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="85688-103">`Me`, `My`, `MyBase`, y `MyClass` en Visual Basic tienen nombres similares, pero con distintos fines.</span><span class="sxs-lookup"><span data-stu-id="85688-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="85688-104">Este tema describe cada una de estas entidades para distinguirlos.</span><span class="sxs-lookup"><span data-stu-id="85688-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="85688-105">Me</span><span class="sxs-lookup"><span data-stu-id="85688-105">Me</span></span>  
 <span data-ttu-id="85688-106">El `Me` palabra clave proporciona una manera de hacer referencia a la instancia específica de una clase o estructura en la que se está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="85688-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="85688-107">`Me` se comporta como una variable de objeto o una variable de estructura que hace referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="85688-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="85688-108">Uso de `Me` es especialmente útil para pasar información sobre la instancia en ejecución de una clase o estructura a un procedimiento de otra clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="85688-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="85688-109">Por ejemplo, suponga que tiene el siguiente procedimiento en un módulo.</span><span class="sxs-lookup"><span data-stu-id="85688-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="85688-110">Puede llamar a este procedimiento y pasar la instancia actual de la <xref:System.Windows.Forms.Form> clase como un argumento mediante la instrucción siguiente.</span><span class="sxs-lookup"><span data-stu-id="85688-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="85688-111">My</span><span class="sxs-lookup"><span data-stu-id="85688-111">My</span></span>  
 <span data-ttu-id="85688-112">El `My` característica proporciona acceso fácil e intuitivo a un número de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] clases, que permite al usuario de Visual Basic interactuar con el equipo, aplicación, configuración, recursos y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="85688-112">The `My` feature provides easy and intuitive access to a number of [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="85688-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="85688-113">MyBase</span></span>  
 <span data-ttu-id="85688-114">El `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase de la instancia actual de una clase base.</span><span class="sxs-lookup"><span data-stu-id="85688-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="85688-115">`MyBase` se utiliza normalmente para tener acceso a los miembros de clase base que se reemplazan o sombrean en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="85688-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="85688-116">`MyBase.New` se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="85688-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="85688-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="85688-117">MyClass</span></span>  
 <span data-ttu-id="85688-118">El `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementaron originalmente.</span><span class="sxs-lookup"><span data-stu-id="85688-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="85688-119">`MyClass` es similar a `Me`, pero todas las llamadas de método en él se tratan como si fuera el método `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="85688-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85688-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="85688-120">See also</span></span>

- [<span data-ttu-id="85688-121">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="85688-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
