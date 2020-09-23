---
title: Me, My, MyBase y MyClass
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
ms.openlocfilehash: cc96f39d9dc37b7f1a5d8205e145869fb1b5ecef
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072241"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="c98c4-102">Me, My, MyBase y MyClass en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c98c4-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>

<span data-ttu-id="c98c4-103">`Me`, `My` , `MyBase` y `MyClass` en Visual Basic tienen nombres similares, pero con fines diferentes.</span><span class="sxs-lookup"><span data-stu-id="c98c4-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="c98c4-104">En este tema se describe cada una de estas entidades con el fin de distinguirlas.</span><span class="sxs-lookup"><span data-stu-id="c98c4-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="c98c4-105">Yo</span><span class="sxs-lookup"><span data-stu-id="c98c4-105">Me</span></span>  

 <span data-ttu-id="c98c4-106">La `Me` palabra clave proporciona una manera de hacer referencia a la instancia específica de una clase o estructura en la que el código se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="c98c4-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="c98c4-107">`Me` se comporta como una variable de objeto o una variable de estructura que hace referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="c98c4-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="c98c4-108">El uso de `Me` es especialmente útil para pasar información sobre la instancia que se está ejecutando actualmente de una clase o estructura a un procedimiento de otra clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="c98c4-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="c98c4-109">Por ejemplo, supongamos que tiene el siguiente procedimiento en un módulo.</span><span class="sxs-lookup"><span data-stu-id="c98c4-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="c98c4-110">Puede llamar a este procedimiento y pasar la instancia actual de la <xref:System.Windows.Forms.Form> clase como argumento mediante la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="c98c4-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="c98c4-111">My</span><span class="sxs-lookup"><span data-stu-id="c98c4-111">My</span></span>  

 <span data-ttu-id="c98c4-112">La `My` característica proporciona acceso sencillo e intuitivo a una serie de clases de .NET Framework, lo que permite al usuario Visual Basic interactuar con el equipo, la aplicación, la configuración, los recursos, etc.</span><span class="sxs-lookup"><span data-stu-id="c98c4-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="c98c4-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="c98c4-113">MyBase</span></span>  

 <span data-ttu-id="c98c4-114">La `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase.</span><span class="sxs-lookup"><span data-stu-id="c98c4-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="c98c4-115">`MyBase` se utiliza normalmente para tener acceso a los miembros de clase base que se invalidan o se sombrean en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c98c4-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="c98c4-116">`MyBase.New` se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c98c4-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="c98c4-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="c98c4-117">MyClass</span></span>  

 <span data-ttu-id="c98c4-118">La `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementó originalmente.</span><span class="sxs-lookup"><span data-stu-id="c98c4-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="c98c4-119">`MyClass` es similar a `Me` , pero todas las llamadas a métodos en él se tratan como si el método fuera `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="c98c4-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c98c4-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c98c4-120">See also</span></span>

- [<span data-ttu-id="c98c4-121">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="c98c4-121">Inheritance Basics</span></span>](../language-features/objects-and-classes/inheritance-basics.md)
