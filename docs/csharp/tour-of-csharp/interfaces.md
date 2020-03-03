---
title: 'Interfaces de C#: un paseo por el lenguaje C#'
description: Las interfaces definen contratos implementados por tipos en C#
ms.date: 02/27/2020
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.openlocfilehash: 62d94462fa481379cf70d63a598deb7f36be204f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159135"
---
# <a name="interfaces"></a><span data-ttu-id="ffcc3-103">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ffcc3-103">Interfaces</span></span>

<span data-ttu-id="ffcc3-104">Una ***interfaz*** define un contrato que se puede implementar mediante clases y structs.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-104">An ***interface*** defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="ffcc3-105">Una interfaz puede contener métodos, propiedades, eventos e indexadores.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-105">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="ffcc3-106">Una interfaz no proporciona implementaciones de los miembros que define, simplemente especifica los miembros que se deben proporcionar mediante clases o estructuras que implementan la interfaz.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-106">An interface doesn't provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>

<span data-ttu-id="ffcc3-107">Las interfaces pueden usar ***herencia múltiple***.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-107">Interfaces may employ ***multiple inheritance***.</span></span> <span data-ttu-id="ffcc3-108">En el ejemplo siguiente, la interfaz `IComboBox` hereda de `ITextBox` y `IListBox`.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-108">In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.</span></span>

[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]

<span data-ttu-id="ffcc3-109">Las clases y los structs pueden implementar varias interfaces.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-109">Classes and structs can implement multiple interfaces.</span></span> <span data-ttu-id="ffcc3-110">En el ejemplo siguiente, la clase `EditBox` implementa `IControl` y `IDataBound`.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-110">In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.</span></span>

[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]

<span data-ttu-id="ffcc3-111">Cuando una clase o un struct implementan una interfaz determinada, las instancias de esa clase o struct se pueden convertir implícitamente a ese tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-111">When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type.</span></span> <span data-ttu-id="ffcc3-112">Por ejemplo</span><span class="sxs-lookup"><span data-stu-id="ffcc3-112">For example</span></span>

[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]

<span data-ttu-id="ffcc3-113">En casos donde una instancia no se conoce estáticamente para implementar una interfaz determinada, se pueden usar conversiones de tipo dinámico.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-113">In cases where an instance isn't statically known to implement a particular interface, dynamic type casts can be used.</span></span> <span data-ttu-id="ffcc3-114">Por ejemplo, las siguientes instrucciones usan conversiones de tipo dinámico para obtener las implementaciones de `IControl` y `IDataBound` de un objeto.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-114">For example, the following statements use dynamic type casts to obtain an object’s `IControl` and `IDataBound` interface implementations.</span></span> <span data-ttu-id="ffcc3-115">Dado que el tipo real en tiempo de ejecución del objeto es `EditBox`, las conversiones se realizan correctamente.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-115">Because the run-time actual type of the object is `EditBox`, the casts succeed.</span></span>

[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]

<span data-ttu-id="ffcc3-116">En la clase `EditBox` anterior, el método `Paint` de la interfaz `IControl` y el método `Bind` de la interfaz `IDataBound` se implementan mediante miembros públicos.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-116">In the previous `EditBox` class, the `Paint` method from the `IControl` interface and the `Bind` method from the `IDataBound` interface are implemented using public members.</span></span> <span data-ttu-id="ffcc3-117">C# también admite ***implementaciones de miembros de interfaz*** explícitos, lo que permite que la clase o el struct eviten que los miembros se conviertan en públicos.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-117">C# also supports explicit ***interface member implementations***, enabling the class or struct to avoid making the members public.</span></span> <span data-ttu-id="ffcc3-118">Una implementación de miembro de interfaz explícito se escribe con el nombre de miembro de interfaz completo.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-118">An explicit interface member implementation is written using the fully qualified interface member name.</span></span> <span data-ttu-id="ffcc3-119">Por ejemplo, la clase `EditBox` podría implementar los métodos `IControl.Paint` y `IDataBound.Bind` mediante implementaciones de miembros de interfaz explícitos del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-119">For example, the `EditBox` class could implement the `IControl.Paint` and `IDataBound.Bind` methods using explicit interface member implementations as follows.</span></span>

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]

<span data-ttu-id="ffcc3-120">Solo se puede acceder a los miembros de interfaz explícitos mediante el tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-120">Explicit interface members can only be accessed via the interface type.</span></span> <span data-ttu-id="ffcc3-121">Por ejemplo, la implementación de `IControl.Paint` proporcionada por la clase EditBox anterior solo se puede invocar si se convierte primero la referencia `EditBox` al tipo de interfaz `IControl`.</span><span class="sxs-lookup"><span data-stu-id="ffcc3-121">For example, the implementation of `IControl.Paint` provided by the previous EditBox class can only be invoked by first converting the `EditBox` reference to the `IControl` interface type.</span></span>

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]

>[!div class="step-by-step"]
><span data-ttu-id="ffcc3-122">[Anterior](arrays.md)
>[Siguiente](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="ffcc3-122">[Previous](arrays.md)
[Next](delegates.md)</span></span>
