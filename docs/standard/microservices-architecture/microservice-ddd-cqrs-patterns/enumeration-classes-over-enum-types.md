---
title: "Uso de las clases de enumeración en lugar de tipos de enumeración"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Uso de las clases de enumeración en lugar de tipos de enumeración"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1745198720fd12a9d26aab2d2afb2c5dd6b6b49d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-enumeration-classes-instead-of-enum-types"></a><span data-ttu-id="519a4-104">Uso de las clases de enumeración en lugar de tipos de enumeración</span><span class="sxs-lookup"><span data-stu-id="519a4-104">Using Enumeration classes instead of enum types</span></span>

<span data-ttu-id="519a4-105">[Enumeraciones](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*enumeraciones* abreviado) son un contenedor de lenguaje fino alrededor de un tipo entero.</span><span class="sxs-lookup"><span data-stu-id="519a4-105">[Enumerations](https://msdn.microsoft.com/en-us/library/sbbt4032.aspx) (*enums* for short) are a thin language wrapper around an integral type.</span></span> <span data-ttu-id="519a4-106">Es posible que desee limitar su uso a para almacenar un valor de un conjunto cerrado de valores.</span><span class="sxs-lookup"><span data-stu-id="519a4-106">You might want to limit their use to when you are storing one value from a closed set of values.</span></span> <span data-ttu-id="519a4-107">La clasificación basada en el género (por ejemplo, hombre, mujer, desconocido) o los tamaños (S, M, L, XL) son buenos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="519a4-107">Classification based on gender (for example, male, female, unknown), or sizes (S, M, L, XL) are good examples.</span></span> <span data-ttu-id="519a4-108">Usar las enumeraciones de flujo de control o abstracciones más sólidas puede ser un [código olor](http://deviq.com/code-smells/).</span><span class="sxs-lookup"><span data-stu-id="519a4-108">Using enums for control flow or more robust abstractions can be a [code smell](http://deviq.com/code-smells/).</span></span> <span data-ttu-id="519a4-109">Este tipo de uso dará lugar a código frágil con muchas instrucciones de flujo de control comprobar los valores de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="519a4-109">This type of usage will lead to fragile code with many control flow statements checking values of the enum.</span></span>

<span data-ttu-id="519a4-110">En su lugar, puede crear clases de enumeración que habilitan todas las características enriquecidas de un lenguaje orientado a objetos.</span><span class="sxs-lookup"><span data-stu-id="519a4-110">Instead, you can create Enumeration classes that enable all the rich features of an object-oriented language.</span></span> <span data-ttu-id="519a4-111">Sin embargo, esto no es un problema crítico y en muchos casos, por simplicidad, se pueden seguir usando enumeraciones regulares si es su preferencia.</span><span class="sxs-lookup"><span data-stu-id="519a4-111">However, this is not a critical issue and in many cases, for simplicity, you can still use regular enums if that is your preference.</span></span>

## <a name="implementing-enumeration-classes"></a><span data-ttu-id="519a4-112">Implementación de clases de enumeración</span><span class="sxs-lookup"><span data-stu-id="519a4-112">Implementing Enumeration classes</span></span>

<span data-ttu-id="519a4-113">La ordenación microservicio en eShopOnContainers proporciona una implementación de clase base de enumeración de ejemplo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="519a4-113">The ordering microservice in eShopOnContainers provides a sample Enumeration base class implementation, as shown in the following example:</span></span>

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }
    public int Id { get; private set; }

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

<span data-ttu-id="519a4-114">Puede utilizar esta clase como un tipo en cualquier objeto de entidad o un valor, como ocurre con la siguiente clase de enumeración de CardType.</span><span class="sxs-lookup"><span data-stu-id="519a4-114">You can use this class as a type in any entity or value object, as for the following CardType Enumeration class.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="519a4-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="519a4-115">Additional resources</span></span>

-   <span data-ttu-id="519a4-116">**Enumeración es contraproducentes: actualizar**
    [*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span><span class="sxs-lookup"><span data-stu-id="519a4-116">**Enum’s are evil—update**
[*http://www.planetgeek.ch/2009/07/01/enums-are-evil/*](http://www.planetgeek.ch/2009/07/01/enums-are-evil/)</span></span>

-   <span data-ttu-id="519a4-117">**Daniel Hardman. Forma de enumeraciones distribuir enfermedad y cómo resolver se**
    [*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span><span class="sxs-lookup"><span data-stu-id="519a4-117">**Daniel Hardman. How Enums Spread Disease — And How To Cure It**
[*https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/*](https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/)</span></span>

-   <span data-ttu-id="519a4-118">**Jimmy Bogard. Las clases de enumeración**
    [*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span><span class="sxs-lookup"><span data-stu-id="519a4-118">**Jimmy Bogard. Enumeration classes**
[*https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/*](https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/)</span></span>

-   <span data-ttu-id="519a4-119">**Steve Smith. Alternativas de enumeración en C#**
    [*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span><span class="sxs-lookup"><span data-stu-id="519a4-119">**Steve Smith. Enum Alternatives in C#**
[*http://ardalis.com/enum-alternatives-in-c*](http://ardalis.com/enum-alternatives-in-c)</span></span>

-   <span data-ttu-id="519a4-120">**Enumeration.cs.**</span><span class="sxs-lookup"><span data-stu-id="519a4-120">**Enumeration.cs.**</span></span> <span data-ttu-id="519a4-121">Clase de enumeración en eShopOnContainers base [ *https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span><span class="sxs-lookup"><span data-stu-id="519a4-121">Base Enumeration class in eShopOnContainers [*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs*](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs)</span></span>

-   <span data-ttu-id="519a4-122">**CardType.cs**.</span><span class="sxs-lookup"><span data-stu-id="519a4-122">**CardType.cs**.</span></span> <span data-ttu-id="519a4-123">Clase de enumeración de ejemplo en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="519a4-123">Sample Enumeration class in eShopOnContainers.</span></span>
    [<span data-ttu-id="519a4-124">*https://github.com/dotnet/eShopOnContainers/BLOB/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span><span class="sxs-lookup"><span data-stu-id="519a4-124">*https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs*</span></span>](https://github.com/dotnet/eShopOnContainers/blob/master/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs)


>[!div class="step-by-step"]
<span data-ttu-id="519a4-125">[Anterior] (implementar-valor-objects.md) [siguiente] (dominio modelo-capa validations.md)</span><span class="sxs-lookup"><span data-stu-id="519a4-125">[Previous] (implement-value-objects.md) [Next] (domain-model-layer-validations.md)</span></span>
