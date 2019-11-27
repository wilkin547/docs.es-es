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
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347338"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="c7b47-102">Me, My, MyBase y MyClass en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7b47-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="c7b47-103">`Me`, `My`, `MyBase`y `MyClass` en Visual Basic tienen nombres similares, pero con fines diferentes.</span><span class="sxs-lookup"><span data-stu-id="c7b47-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="c7b47-104">En este tema se describe cada una de estas entidades con el fin de distinguirlas.</span><span class="sxs-lookup"><span data-stu-id="c7b47-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="c7b47-105">Me</span><span class="sxs-lookup"><span data-stu-id="c7b47-105">Me</span></span>  
 <span data-ttu-id="c7b47-106">La palabra clave `Me` proporciona una manera de hacer referencia a la instancia específica de una clase o estructura en la que se está ejecutando el código.</span><span class="sxs-lookup"><span data-stu-id="c7b47-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="c7b47-107">`Me` se comporta como una variable de objeto o una variable de estructura que hace referencia a la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="c7b47-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="c7b47-108">El uso de `Me` es especialmente útil para pasar información sobre la instancia que se está ejecutando actualmente de una clase o estructura a un procedimiento de otra clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="c7b47-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="c7b47-109">Por ejemplo, supongamos que tiene el siguiente procedimiento en un módulo.</span><span class="sxs-lookup"><span data-stu-id="c7b47-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="c7b47-110">Puede llamar a este procedimiento y pasar la instancia actual de la clase <xref:System.Windows.Forms.Form> como argumento mediante la siguiente instrucción.</span><span class="sxs-lookup"><span data-stu-id="c7b47-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="c7b47-111">My</span><span class="sxs-lookup"><span data-stu-id="c7b47-111">My</span></span>  
 <span data-ttu-id="c7b47-112">La característica `My` proporciona acceso sencillo e intuitivo a una serie de clases de .NET Framework, lo que permite al usuario de Visual Basic interactuar con el equipo, la aplicación, la configuración, los recursos, etc.</span><span class="sxs-lookup"><span data-stu-id="c7b47-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="c7b47-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="c7b47-113">MyBase</span></span>  
 <span data-ttu-id="c7b47-114">La palabra clave `MyBase` se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase.</span><span class="sxs-lookup"><span data-stu-id="c7b47-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="c7b47-115">`MyBase` se usa normalmente para tener acceso a los miembros de clase base que se invalidan o se sombrean en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c7b47-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="c7b47-116">`MyBase.New` se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c7b47-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="c7b47-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="c7b47-117">MyClass</span></span>  
 <span data-ttu-id="c7b47-118">La palabra clave `MyClass` se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementó originalmente.</span><span class="sxs-lookup"><span data-stu-id="c7b47-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="c7b47-119">`MyClass` es similar a `Me`, pero todas las llamadas al método en él se tratan como si se `NotOverridable`el método.</span><span class="sxs-lookup"><span data-stu-id="c7b47-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7b47-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7b47-120">See also</span></span>

- [<span data-ttu-id="c7b47-121">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="c7b47-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
