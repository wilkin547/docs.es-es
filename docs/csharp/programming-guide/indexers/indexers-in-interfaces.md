---
title: 'Indizadores en interfaces: Guía de programación de C#'
ms.date: 02/08/2020
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 9ce6e4f0e0533c2880c6241f44409435248a336a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287485"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="8623b-102">Indizadores en interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8623b-102">Indexers in Interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="8623b-103">Los indexadores se pueden declarar en una [interfaz](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="8623b-103">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="8623b-104">Los descriptores de acceso de los indexadores de interfaz se diferencian de los descriptores de acceso de los indexadores de [clase](../../language-reference/keywords/class.md) de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="8623b-104">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>

- <span data-ttu-id="8623b-105">Los descriptores de acceso de interfaz no usan modificadores.</span><span class="sxs-lookup"><span data-stu-id="8623b-105">Interface accessors do not use modifiers.</span></span>
- <span data-ttu-id="8623b-106">Normalmente, un descriptor de acceso de interfaz no tiene un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8623b-106">An interface accessor typically does not have a body.</span></span>

<span data-ttu-id="8623b-107">El propósito del descriptor de acceso es indicar si el indizador es de lectura y escritura, de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="8623b-107">The purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span> <span data-ttu-id="8623b-108">Puede proporcionar una implementación para un indizador definido en una interfaz, pero esto es poco frecuente.</span><span class="sxs-lookup"><span data-stu-id="8623b-108">You may provide an implementation for an indexer defined in an interface, but this is rare.</span></span> <span data-ttu-id="8623b-109">Los indizadores suelen definir una API para acceder a los campos de datos y los campos de datos no se pueden definir en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="8623b-109">Indexers typically define an API to access data fields, and data fields cannot be defined in an interface.</span></span>

<span data-ttu-id="8623b-110">A continuación tiene un ejemplo de un descriptor de acceso de indexador de interfaz:</span><span class="sxs-lookup"><span data-stu-id="8623b-110">The following is an example of an interface indexer accessor:</span></span>

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#DefineIndexer)]

<span data-ttu-id="8623b-111">La firma de un indexador debe ser diferente de las firmas de los demás indexadores declarados en la misma interfaz.</span><span class="sxs-lookup"><span data-stu-id="8623b-111">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>

## <a name="example"></a><span data-ttu-id="8623b-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8623b-112">Example</span></span>

<span data-ttu-id="8623b-113">En el siguiente ejemplo, se muestra cómo implementar indexadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="8623b-113">The following example shows how to implement interface indexers.</span></span>

[!code-csharp[Implement](~/samples/snippets/csharp/interfaces/indexers.cs#ImplementInterface)]

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#ExampleCode)]

<span data-ttu-id="8623b-114">En el ejemplo anterior, podría usar la implementación del miembro de interfaz explícita al usar el nombre completo del miembro de interfaz.</span><span class="sxs-lookup"><span data-stu-id="8623b-114">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="8623b-115">Por ejemplo</span><span class="sxs-lookup"><span data-stu-id="8623b-115">For example</span></span>

```csharp
string IIndexInterface.this[int index]
{
}
```

<span data-ttu-id="8623b-116">En cambio, el nombre completo solo es necesario para evitar la ambigüedad cuando la clase implementa más de una interfaz con la misma firma de indexador.</span><span class="sxs-lookup"><span data-stu-id="8623b-116">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="8623b-117">Por ejemplo, si una clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee` y ambas interfaces tienen la misma firma de indexador, la implementación del miembro de interfaz explícita es necesaria.</span><span class="sxs-lookup"><span data-stu-id="8623b-117">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="8623b-118">Es decir, la siguiente declaración de indexador:</span><span class="sxs-lookup"><span data-stu-id="8623b-118">That is, the following indexer declaration:</span></span>

```csharp
string IEmployee.this[int index]
{
}
```

<span data-ttu-id="8623b-119">implementa el indexador en la interfaz `IEmployee`, mientras que la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="8623b-119">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>

```csharp
string ICitizen.this[int index]
{
}
```

<span data-ttu-id="8623b-120">implementa el indexador en la interfaz `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="8623b-120">implements the indexer on the `ICitizen` interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="8623b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="8623b-121">See also</span></span>

- [<span data-ttu-id="8623b-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8623b-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8623b-123">Indizadores</span><span class="sxs-lookup"><span data-stu-id="8623b-123">Indexers</span></span>](./index.md)
- [<span data-ttu-id="8623b-124">Propiedades</span><span class="sxs-lookup"><span data-stu-id="8623b-124">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="8623b-125">Interfaces</span><span class="sxs-lookup"><span data-stu-id="8623b-125">Interfaces</span></span>](../interfaces/index.md)
