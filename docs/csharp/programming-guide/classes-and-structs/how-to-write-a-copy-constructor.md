---
title: Procedimiento para escribir un constructor de copia - Guía de programación de C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: aa6feb1b07f491a90a78684e254910d387b9bccd
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714852"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="5930c-102">Procedimiento para escribir un constructor de copia (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5930c-102">How to write a copy constructor (C# Programming Guide)</span></span>
<span data-ttu-id="5930c-103">C# no proporciona un constructor de copias para los objetos, pero puede escribir uno personalmente.</span><span class="sxs-lookup"><span data-stu-id="5930c-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5930c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5930c-104">Example</span></span>  
 <span data-ttu-id="5930c-105">En el ejemplo siguiente, `Person`[class](../../language-reference/keywords/class.md) define un constructor de copias que toma, como argumento, una instancia de `Person`.</span><span class="sxs-lookup"><span data-stu-id="5930c-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="5930c-106">Los valores de las propiedades de los argumentos se asignan a las propiedades de la nueva instancia de `Person`.</span><span class="sxs-lookup"><span data-stu-id="5930c-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="5930c-107">El código contiene un constructor de copias alternativo que envía las propiedades `Name` y `Age` de la instancia que quiere copiar al constructor de instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="5930c-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="5930c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5930c-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="5930c-109">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5930c-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5930c-110">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="5930c-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="5930c-111">Constructores</span><span class="sxs-lookup"><span data-stu-id="5930c-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="5930c-112">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="5930c-112">Finalizers</span></span>](./destructors.md)
