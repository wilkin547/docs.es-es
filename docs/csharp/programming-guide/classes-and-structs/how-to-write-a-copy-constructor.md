---
title: Procedimiento para escribir un constructor de copia - Guía de programación de C#
description: Aprenda a escribir un constructor de copia en C# que toma una instancia de clase y devuelve una nueva instancia con los valores de la entrada.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: 52fd5aedea6a0e3b7c22e20db523329a00bba9ad
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204013"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="0cb74-103">Procedimiento para escribir un constructor de copia (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0cb74-103">How to write a copy constructor (C# Programming Guide)</span></span>

<span data-ttu-id="0cb74-104">C# no proporciona un constructor de copias para los objetos, pero puede escribir uno personalmente.</span><span class="sxs-lookup"><span data-stu-id="0cb74-104">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cb74-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0cb74-105">Example</span></span>  

 <span data-ttu-id="0cb74-106">En el ejemplo siguiente, `Person`[class](../../language-reference/keywords/class.md) define un constructor de copias que toma, como argumento, una instancia de `Person`.</span><span class="sxs-lookup"><span data-stu-id="0cb74-106">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="0cb74-107">Los valores de las propiedades de los argumentos se asignan a las propiedades de la nueva instancia de `Person`.</span><span class="sxs-lookup"><span data-stu-id="0cb74-107">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="0cb74-108">El código contiene un constructor de copias alternativo que envía las propiedades `Name` y `Age` de la instancia que quiere copiar al constructor de instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="0cb74-108">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="0cb74-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cb74-109">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="0cb74-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0cb74-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0cb74-111">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="0cb74-111">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="0cb74-112">Constructores</span><span class="sxs-lookup"><span data-stu-id="0cb74-112">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="0cb74-113">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="0cb74-113">Finalizers</span></span>](./destructors.md)
