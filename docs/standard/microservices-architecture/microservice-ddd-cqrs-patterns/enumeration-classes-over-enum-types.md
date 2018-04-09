---
title: Uso de las clases de enumeración en lugar de los tipos de enumeración
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Uso de las clases de enumeración en lugar de los tipos de enumeración
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 57ff60ea01421f1a2a0466b7de9716b72b02d2c1
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="d6cec-104">Uso de las clases de enumeración en lugar de los tipos de enumeración</span><span class="sxs-lookup"><span data-stu-id="d6cec-104">Using enumeration classes instead of enum types</span></span>

<span data-ttu-id="d6cec-105">Las [enumeraciones](../../../../docs/csharp/language-reference/keywords/enum.md) (o *tipos enum* abreviado) son un contenedor de lenguaje fino alrededor de un tipo entero.</span><span class="sxs-lookup"><span data-stu-id="d6cec-105">[Enumerations](../../../../docs/csharp/language-reference/keywords/enum.md) (or *enum types* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="d6cec-106">Es posible que quiera limitar su uso al momento en que almacena un valor de un conjunto cerrado de valores.</span><span class="sxs-lookup"><span data-stu-id="d6cec-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="d6cec-107">La clasificación basada en el género (por ejemplo, hombre, mujer, desconocido) o el tamaño (pequeño, mediano, grande) son buenos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="d6cec-107">Classification based on gender (for example, male, female, unknown) or sizes (small, medium, large) are good examples.</span></span> <span data-ttu-id="d6cec-108">Usar las enumeraciones para el flujo de control o abstracciones más sólidas puede producir un [problema en el código](http://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="d6cec-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="d6cec-109">Este tipo de uso da lugar a código frágil con muchas instrucciones de flujo de control que comprueban los valores de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="d6cec-109">This type of usage leads to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="d6cec-110">En su lugar, puede crear clases de enumeración que habilitan todas las características enriquecidas de un lenguaje orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="d6cec-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span>

<span data-ttu-id="d6cec-111">Sin embargo, esto no es un tema crítico y, en muchos casos, por simplicidad, puede seguir usando [tipos enum](../../../../docs/csharp/language-reference/keywords/enum.md) normales si lo prefiere.</span><span class="sxs-lookup"><span data-stu-id="d6cec-111">However, this isn't a critical topic and in many cases, for simplicity, you can still use regular [enum types](../../../../docs/csharp/language-reference/keywords/enum.md) if that's your preference.</span></span>

## <a name="implementing-an-enumeration-base-class"></a><span data-ttu-id="d6cec-112">Implementación de una clase base de enumeración</span><span class="sxs-lookup"><span data-stu-id="d6cec-112">Implementing an Enumeration base class</span></span>

<span data-ttu-id="d6cec-113">El microservicio de pedidos en eShopOnContainers proporciona una implementación de clase base de enumeración de ejemplo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6cec-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; }
    public int Id { get; }

    protected Enumeration()
    {
    }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString()
    {
        return Name;
    }

    public static IEnumerable<T> GetAll<T>() where T : Enumeration, new()
    {
        var type = typeof(T);
        var fields = type.GetTypeInfo().GetFields(BindingFlags.Public |
            BindingFlags.Static |
            BindingFlags.DeclaredOnly);
        foreach (var info in fields)
        {
            var instance = new T();
            var locatedValue = info.GetValue(instance) as T;
            if (locatedValue != null)
            {
                yield return locatedValue;
            }
        }
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;
        if (otherValue == null)
        {
            return false;
        }
        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);
        return typeMatches && valueMatches;
    }

    public int CompareTo(object other)
    {
        return Id.CompareTo(((Enumeration)other).Id);
    }

    // Other utility methods ...
}
```

<span data-ttu-id="d6cec-114">Puede usar esta clase como un tipo en cualquier entidad u objeto de valor, como ocurre con la clase de enumeración CardType siguiente:</span><span class="sxs-lookup"><span data-stu-id="d6cec-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class:</span></span>

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    protected CardType() { }

    public CardType(int id, string name)
        : base(id, name)
    {
    }

    public static IEnumerable<CardType> List()
    {
        return new[] { Amex, Visa, MasterCard };
    }
    // Other util methods
}
```

## <a name="additional-resources"></a><span data-ttu-id="d6cec-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d6cec-115">Additional resources</span></span>

-   <span data-ttu-id="d6cec-116">**Enum’s are evil—update**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/) (Las enumeraciones son contraproducentes: actualice)</span><span class="sxs-lookup"><span data-stu-id="d6cec-116">**Enum’s are evil—update**
[*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="d6cec-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/) (Cómo las enumeraciones contagian la enfermedad y cómo curarla)</span><span class="sxs-lookup"><span data-stu-id="d6cec-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="d6cec-118">**Jimmy Bogard. Enumeration classes**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/) (Clases de enumeración)</span><span class="sxs-lookup"><span data-stu-id="d6cec-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="d6cec-119">**Steve Smith. Enum Alternatives in C#**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c) (Alternativas de enumeración en C#)</span><span class="sxs-lookup"><span data-stu-id="d6cec-119">**Steve Smith. Enum Alternatives in C#**
[*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="d6cec-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="d6cec-120">**Enumeration.cs.**</span></span> <span data-ttu-id="d6cec-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs) (Clase base de enumeración en eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="d6cec-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="d6cec-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="d6cec-122">**CardType.cs**.</span></span> <span data-ttu-id="d6cec-123">Sample Enumeration class in eShopOnContainers (CardType.cs. Clase de enumeración de ejemplo en eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="d6cec-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="d6cec-124">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span><span class="sxs-lookup"><span data-stu-id="d6cec-124">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
