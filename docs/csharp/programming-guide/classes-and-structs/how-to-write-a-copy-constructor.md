---
title: Procedimiento para escribir un constructor de copia - Guía de programación de C#
description: Aprenda a escribir un constructor de copia en C# que toma una instancia de clase y devuelve una nueva instancia con los valores de la entrada.
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, copy constructor
- copy constructor [C#]
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
ms.openlocfilehash: c61018444dd600d6f33765b104034355d0301667
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255241"
---
# <a name="how-to-write-a-copy-constructor-c-programming-guide"></a><span data-ttu-id="60f26-103">Procedimiento para escribir un constructor de copia (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="60f26-103">How to write a copy constructor (C# Programming Guide)</span></span>

<span data-ttu-id="60f26-104">Los [registros](records.md) de C# proporcionan un constructor de copia para objetos, pero debe escribir uno para las clases personalmente.</span><span class="sxs-lookup"><span data-stu-id="60f26-104">C# [records](records.md) provide a copy constructor for objects, but for classes you have to write one yourself.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60f26-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60f26-105">Example</span></span>  

 <span data-ttu-id="60f26-106">En el ejemplo siguiente, `Person`[class](../../language-reference/keywords/class.md) define un constructor de copias que toma, como argumento, una instancia de `Person`.</span><span class="sxs-lookup"><span data-stu-id="60f26-106">In the following example, the `Person`[class](../../language-reference/keywords/class.md) defines a copy constructor that takes, as its argument, an instance of `Person`.</span></span> <span data-ttu-id="60f26-107">Los valores de las propiedades de los argumentos se asignan a las propiedades de la nueva instancia de `Person`.</span><span class="sxs-lookup"><span data-stu-id="60f26-107">The values of the properties of the argument are assigned to the properties of the new instance of `Person`.</span></span> <span data-ttu-id="60f26-108">El código contiene un constructor de copias alternativo que envía las propiedades `Name` y `Age` de la instancia que quiere copiar al constructor de instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="60f26-108">The code contains an alternative copy constructor that sends the `Name` and `Age` properties of the instance that you want to copy to the instance constructor of the class.</span></span>  
  
 [!code-csharp[CopyConstructor](snippets/how-to-write-a-copy-constructor/Program.cs)]

## <a name="see-also"></a><span data-ttu-id="60f26-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="60f26-109">See also</span></span>

- <xref:System.ICloneable>
- [<span data-ttu-id="60f26-110">Registros</span><span class="sxs-lookup"><span data-stu-id="60f26-110">Records</span></span>](records.md)
- [<span data-ttu-id="60f26-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="60f26-111">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="60f26-112">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="60f26-112">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="60f26-113">Constructores</span><span class="sxs-lookup"><span data-stu-id="60f26-113">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="60f26-114">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="60f26-114">Finalizers</span></span>](./destructors.md)
