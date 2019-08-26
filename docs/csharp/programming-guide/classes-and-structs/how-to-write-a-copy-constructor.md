---
title: 'Procedimiento Escribir un constructor Copy: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: bdc352566052f4cec1686176131e9b1e1b768794
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596606"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="67e97-102">Procedimiento Escribir un constructor Copy (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="67e97-102">How to: Write a Copy Constructor (C# Programming Guide)</span></span>
<span data-ttu-id="67e97-103">C# no proporciona un constructor de copias para los objetos, pero puede escribir uno personalmente.</span><span class="sxs-lookup"><span data-stu-id="67e97-103">C# doesn't provide a copy constructor for objects, but you can write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67e97-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67e97-104">Example</span></span>  
 <span data-ttu-id="67e97-105">En el ejemplo siguiente, `Person`[class](../../language-reference/keywords/class.md) define un constructor de copias que toma, como argumento, una instancia de `Person`.</span><span class="sxs-lookup"><span data-stu-id="67e97-105">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="67e97-106">Los valores de las propiedades de los argumentos se asignan a las propiedades de la nueva instancia de `Person`.</span><span class="sxs-lookup"><span data-stu-id="67e97-106">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="67e97-107">El código contiene un constructor de copias alternativo que envía las propiedades `Name` y `Age` de la instancia que quiere copiar al constructor de instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="67e97-107">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[csProgGuideObjects#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#16)]  
  
## <a name="see-also"></a><span data-ttu-id="67e97-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="67e97-108">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="67e97-109">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="67e97-109">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="67e97-110">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="67e97-110">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="67e97-111">Constructores</span><span class="sxs-lookup"><span data-stu-id="67e97-111">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="67e97-112">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="67e97-112">Finalizers</span></span>](./destructors.md)
