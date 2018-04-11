---
title: 'Atributos de C#: un paseo por el lenguaje C#'
description: Obtenga información sobre la programación declarativa usando atributos en C#
keywords: . NET, csharp
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 753bcfe2-7ddd-4487-9513-ba70937fc8e9
ms.openlocfilehash: 6878a408ef892ee47a03bfa04f736b9bf9671696
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="attributes"></a><span data-ttu-id="32fd2-104">Atributos</span><span class="sxs-lookup"><span data-stu-id="32fd2-104">Attributes</span></span>

<span data-ttu-id="32fd2-105">Los tipos, los miembros y otras entidades en un programa de C # admiten modificadores que controlan ciertos aspectos de su comportamiento.</span><span class="sxs-lookup"><span data-stu-id="32fd2-105">Types, members, and other entities in a C# program support modifiers that control certain aspects of their behavior.</span></span> <span data-ttu-id="32fd2-106">Por ejemplo, la accesibilidad de un método se controla mediante los modificadores `public`, `protected`, `internal` y `private`.</span><span class="sxs-lookup"><span data-stu-id="32fd2-106">For example, the accessibility of a method is controlled using the `public`, `protected`, `internal`, and `private` modifiers.</span></span> <span data-ttu-id="32fd2-107">C # generaliza esta funcionalidad de manera que los tipos de información declarativa definidos por el usuario se puedan adjuntar a las entidades del programa y recuperarse en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="32fd2-107">C# generalizes this capability such that user-defined types of declarative information can be attached to program entities and retrieved at run-time.</span></span> <span data-ttu-id="32fd2-108">Los programas especifican esta información declarativa adicional mediante la definición y el uso de ***atributos***.</span><span class="sxs-lookup"><span data-stu-id="32fd2-108">Programs specify this additional declarative information by defining and using ***attributes***.</span></span>

<span data-ttu-id="32fd2-109">En el ejemplo siguiente se declara un atributo `HelpAttribute` que se puede colocar en entidades de programa para proporcionar vínculos a la documentación asociada.</span><span class="sxs-lookup"><span data-stu-id="32fd2-109">The following example declares a `HelpAttribute` attribute that can be placed on program entities to provide links to their associated documentation.</span></span>

[!code-csharp[AttributeDefined](../../../samples/snippets/csharp/tour/attributes/Program.cs#L3-L20)]

<span data-ttu-id="32fd2-110">Todas las clases de atributos se derivan de la clase base <xref:System.Attribute> proporcionada por la biblioteca estándar.</span><span class="sxs-lookup"><span data-stu-id="32fd2-110">All attribute classes derive from the <xref:System.Attribute> base class provided by the standard library.</span></span> <span data-ttu-id="32fd2-111">Los atributos se pueden aplicar proporcionando su nombre, junto con cualquier argumento, entre corchetes, justo antes de la declaración asociada.</span><span class="sxs-lookup"><span data-stu-id="32fd2-111">Attributes can be applied by giving their name, along with any arguments, inside square brackets just before the associated declaration.</span></span> <span data-ttu-id="32fd2-112">Si el nombre de un atributo termina en `Attribute`, esa parte del nombre se puede omitir cuando se hace referencia al atributo.</span><span class="sxs-lookup"><span data-stu-id="32fd2-112">If an attribute’s name ends in `Attribute`, that part of the name can be omitted when the attribute is referenced.</span></span> <span data-ttu-id="32fd2-113">Por ejemplo, el atributo `HelpAttribute` se puede usar de la manera siguiente.</span><span class="sxs-lookup"><span data-stu-id="32fd2-113">For example, the `HelpAttribute` attribute can be used as follows.</span></span>

[!code-csharp[AttributeApplied](../../../samples/snippets/csharp/tour/attributes/Program.cs#L22-L28)]

<span data-ttu-id="32fd2-114">En este ejemplo se adjunta un atributo `HelpAttribute` a la clase `Widget`.</span><span class="sxs-lookup"><span data-stu-id="32fd2-114">This example attaches a `HelpAttribute` to the `Widget` class.</span></span> <span data-ttu-id="32fd2-115">También se agrega otro atributo `HelpAttribute` al método `Display` en la clase.</span><span class="sxs-lookup"><span data-stu-id="32fd2-115">It adds another `HelpAttribute` to the `Display` method in the class.</span></span> <span data-ttu-id="32fd2-116">Los constructores públicos de una clase de atributos controlan la información que se debe proporcionar cuando el atributo se adjunta a una entidad de programa.</span><span class="sxs-lookup"><span data-stu-id="32fd2-116">The public constructors of an attribute class control the information that must be provided when the attribute is attached to a program entity.</span></span> <span data-ttu-id="32fd2-117">Se puede proporcionar información adicional haciendo referencia a las propiedades públicas de lectura y escritura de la clase de atributos (como la referencia a la propiedad `Topic` usada anteriormente).</span><span class="sxs-lookup"><span data-stu-id="32fd2-117">Additional information can be provided by referencing public read-write properties of the attribute class (such as the reference to the `Topic` property previously).</span></span>

<span data-ttu-id="32fd2-118">Cuando se solicita un atributo determinado mediante reflexión, se invoca al constructor de la clase de atributos con la información proporcionada en el origen del programa y se devuelve la instancia de atributo resultante.</span><span class="sxs-lookup"><span data-stu-id="32fd2-118">When a particular attribute is requested through reflection, the constructor for the attribute class is invoked with the information provided in the program source, and the resulting attribute instance is returned.</span></span> <span data-ttu-id="32fd2-119">Si se proporciona información adicional mediante propiedades, dichas propiedades se establecen en los valores dados antes de devolver la instancia del atributo.</span><span class="sxs-lookup"><span data-stu-id="32fd2-119">If additional information was provided through properties, those properties are set to the given values before the attribute instance is returned.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="32fd2-120">Anterior</span><span class="sxs-lookup"><span data-stu-id="32fd2-120">Previous</span></span>](delegates.md)
