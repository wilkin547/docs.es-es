---
title: 'Cómo: Escribir un constructor Copy (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 8a7cc85d40272918f4839d13fcccb79b558eeac7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322502"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="02629-102">Cómo: Escribir un constructor Copy (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="02629-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="02629-103">C# no proporciona un constructor de copias para los objetos, pero puede escribir uno personalmente.</span><span class="sxs-lookup"><span data-stu-id="02629-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02629-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02629-104">Example</span></span>  
 <span data-ttu-id="02629-105">En el ejemplo siguiente, `Person`[class](../../../csharp/language-reference/keywords/class.md) define un constructor de copias que toma, como argumento, una instancia de `Person`.</span><span class="sxs-lookup"><span data-stu-id="02629-105">In the following example, the `Person`[class](../../../csharp/language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="02629-106">Los valores de las propiedades de los argumentos se asignan a las propiedades de la nueva instancia de `Person`.</span><span class="sxs-lookup"><span data-stu-id="02629-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="02629-107">El código contiene un constructor de copias alternativo que envía las propiedades `Name` y `Age` de la instancia que quiere copiar al constructor de instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="02629-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="02629-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="02629-108">See Also</span></span>  
 <xref:System.ICloneable>  
 [<span data-ttu-id="02629-109">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="02629-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="02629-110">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="02629-110">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="02629-111">Constructores</span><span class="sxs-lookup"><span data-stu-id="02629-111">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="02629-112">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="02629-112">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
