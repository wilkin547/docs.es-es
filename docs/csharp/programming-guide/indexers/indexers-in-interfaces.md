---
title: 'Indizadores en interfaces: Guía de programación de C#'
ms.date: 02/08/2020
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 667a4213626ee37bfc5bf8c4fe78c2cf7186a73e
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627843"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="9fdae-102">Indizadores en interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9fdae-102">Indexers in Interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="9fdae-103">Los indexadores se pueden declarar en una [interfaz](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="9fdae-103">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="9fdae-104">Los descriptores de acceso de los indexadores de interfaz se diferencian de los descriptores de acceso de los indexadores de [clase](../../language-reference/keywords/class.md) de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="9fdae-104">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>

- <span data-ttu-id="9fdae-105">Los descriptores de acceso de interfaz no usan modificadores.</span><span class="sxs-lookup"><span data-stu-id="9fdae-105">Interface accessors do not use modifiers.</span></span>
- <span data-ttu-id="9fdae-106">Normalmente, un descriptor de acceso de interfaz no tiene un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="9fdae-106">An interface accessor typically does not have a body.</span></span>

<span data-ttu-id="9fdae-107">El propósito del descriptor de acceso es indicar si el indizador es de lectura y escritura, de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="9fdae-107">The purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span> <span data-ttu-id="9fdae-108">Puede proporcionar una implementación para un indizador definido en una interfaz, pero esto es poco frecuente.</span><span class="sxs-lookup"><span data-stu-id="9fdae-108">You may provide an implementation for an indexer defined in an interface, but this is rare.</span></span> <span data-ttu-id="9fdae-109">Los indizadores suelen definir una API para acceder a los campos de datos y los campos de datos no se pueden definir en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="9fdae-109">Indexers typically define an API to access data fields, and data fields cannot be defined in an interface.</span></span>

<span data-ttu-id="9fdae-110">A continuación tiene un ejemplo de un descriptor de acceso de indexador de interfaz:</span><span class="sxs-lookup"><span data-stu-id="9fdae-110">The following is an example of an interface indexer accessor:</span></span>

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#DefineIndexer)]

<span data-ttu-id="9fdae-111">La firma de un indexador debe ser diferente de las firmas de los demás indexadores declarados en la misma interfaz.</span><span class="sxs-lookup"><span data-stu-id="9fdae-111">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>

## <a name="example"></a><span data-ttu-id="9fdae-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fdae-112">Example</span></span>

<span data-ttu-id="9fdae-113">En el siguiente ejemplo, se muestra cómo implementar indexadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="9fdae-113">The following example shows how to implement interface indexers.</span></span>

[!code-csharp[Implement](~/samples/snippets/csharp/interfaces/indexers.cs#ImplementInterface)]

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#ExampleCode)]

<span data-ttu-id="9fdae-114">En el ejemplo anterior, podría usar la implementación del miembro de interfaz explícita al usar el nombre completo del miembro de interfaz.</span><span class="sxs-lookup"><span data-stu-id="9fdae-114">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="9fdae-115">Por ejemplo</span><span class="sxs-lookup"><span data-stu-id="9fdae-115">For example</span></span>

```csharp
string IIndexInterface.this[int index]
{
}
```

<span data-ttu-id="9fdae-116">En cambio, el nombre completo solo es necesario para evitar la ambigüedad cuando la clase implementa más de una interfaz con la misma firma de indexador.</span><span class="sxs-lookup"><span data-stu-id="9fdae-116">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="9fdae-117">Por ejemplo, si una clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee` y ambas interfaces tienen la misma firma de indexador, la implementación del miembro de interfaz explícita es necesaria.</span><span class="sxs-lookup"><span data-stu-id="9fdae-117">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="9fdae-118">Es decir, la siguiente declaración de indexador:</span><span class="sxs-lookup"><span data-stu-id="9fdae-118">That is, the following indexer declaration:</span></span>

```csharp
string IEmployee.this[int index]
{
}
``

implements the indexer on the `IEmployee` interface, while the following declaration:

```csharp
string ICitizen.this[int index]
{
}
```

<span data-ttu-id="9fdae-119">implementa el indexador en la interfaz `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="9fdae-119">implements the indexer on the `ICitizen` interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="9fdae-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fdae-120">See also</span></span>

- [<span data-ttu-id="9fdae-121">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9fdae-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9fdae-122">Indizadores</span><span class="sxs-lookup"><span data-stu-id="9fdae-122">Indexers</span></span>](./index.md)
- [<span data-ttu-id="9fdae-123">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9fdae-123">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="9fdae-124">Interfaces</span><span class="sxs-lookup"><span data-stu-id="9fdae-124">Interfaces</span></span>](../interfaces/index.md)
