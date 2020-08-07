---
title: 'Indizadores en interfaces: Guía de programación de C#'
description: Los indexadores se pueden declarar en una interfaz de C#. Conozca de qué modo los descriptores de acceso de los indexadores de interfaz se diferencian de los descriptores de acceso de los indexadores de clase.
ms.date: 02/08/2020
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: ec77843bdf3181a543bd6c02cfb034b21ded1ae7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303106"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="9abaa-104">Indizadores en interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9abaa-104">Indexers in Interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="9abaa-105">Los indexadores se pueden declarar en una [interfaz](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="9abaa-105">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="9abaa-106">Los descriptores de acceso de los indexadores de interfaz se diferencian de los descriptores de acceso de los indexadores de [clase](../../language-reference/keywords/class.md) de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="9abaa-106">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>

- <span data-ttu-id="9abaa-107">Los descriptores de acceso de interfaz no usan modificadores.</span><span class="sxs-lookup"><span data-stu-id="9abaa-107">Interface accessors do not use modifiers.</span></span>
- <span data-ttu-id="9abaa-108">Normalmente, un descriptor de acceso de interfaz no tiene un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="9abaa-108">An interface accessor typically does not have a body.</span></span>

<span data-ttu-id="9abaa-109">El propósito del descriptor de acceso es indicar si el indizador es de lectura y escritura, de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="9abaa-109">The purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span> <span data-ttu-id="9abaa-110">Puede proporcionar una implementación para un indizador definido en una interfaz, pero esto es poco frecuente.</span><span class="sxs-lookup"><span data-stu-id="9abaa-110">You may provide an implementation for an indexer defined in an interface, but this is rare.</span></span> <span data-ttu-id="9abaa-111">Los indizadores suelen definir una API para acceder a los campos de datos y los campos de datos no se pueden definir en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="9abaa-111">Indexers typically define an API to access data fields, and data fields cannot be defined in an interface.</span></span>

<span data-ttu-id="9abaa-112">A continuación tiene un ejemplo de un descriptor de acceso de indexador de interfaz:</span><span class="sxs-lookup"><span data-stu-id="9abaa-112">The following is an example of an interface indexer accessor:</span></span>

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#DefineIndexer)]

<span data-ttu-id="9abaa-113">La firma de un indexador debe ser diferente de las firmas de los demás indexadores declarados en la misma interfaz.</span><span class="sxs-lookup"><span data-stu-id="9abaa-113">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>

## <a name="example"></a><span data-ttu-id="9abaa-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9abaa-114">Example</span></span>

<span data-ttu-id="9abaa-115">En el siguiente ejemplo, se muestra cómo implementar indexadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="9abaa-115">The following example shows how to implement interface indexers.</span></span>

[!code-csharp[Implement](~/samples/snippets/csharp/interfaces/indexers.cs#ImplementInterface)]

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#ExampleCode)]

<span data-ttu-id="9abaa-116">En el ejemplo anterior, podría usar la implementación del miembro de interfaz explícita al usar el nombre completo del miembro de interfaz.</span><span class="sxs-lookup"><span data-stu-id="9abaa-116">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="9abaa-117">Por ejemplo</span><span class="sxs-lookup"><span data-stu-id="9abaa-117">For example</span></span>

```csharp
string IIndexInterface.this[int index]
{
}
```

<span data-ttu-id="9abaa-118">En cambio, el nombre completo solo es necesario para evitar la ambigüedad cuando la clase implementa más de una interfaz con la misma firma de indexador.</span><span class="sxs-lookup"><span data-stu-id="9abaa-118">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="9abaa-119">Por ejemplo, si una clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee` y ambas interfaces tienen la misma firma de indexador, la implementación del miembro de interfaz explícita es necesaria.</span><span class="sxs-lookup"><span data-stu-id="9abaa-119">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="9abaa-120">Es decir, la siguiente declaración de indexador:</span><span class="sxs-lookup"><span data-stu-id="9abaa-120">That is, the following indexer declaration:</span></span>

```csharp
string IEmployee.this[int index]
{
}
```

<span data-ttu-id="9abaa-121">implementa el indexador en la interfaz `IEmployee`, mientras que la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="9abaa-121">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>

```csharp
string ICitizen.this[int index]
{
}
```

<span data-ttu-id="9abaa-122">implementa el indexador en la interfaz `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="9abaa-122">implements the indexer on the `ICitizen` interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="9abaa-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9abaa-123">See also</span></span>

- [<span data-ttu-id="9abaa-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9abaa-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9abaa-125">Indizadores</span><span class="sxs-lookup"><span data-stu-id="9abaa-125">Indexers</span></span>](./index.md)
- [<span data-ttu-id="9abaa-126">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9abaa-126">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="9abaa-127">Interfaces</span><span class="sxs-lookup"><span data-stu-id="9abaa-127">Interfaces</span></span>](../interfaces/index.md)
