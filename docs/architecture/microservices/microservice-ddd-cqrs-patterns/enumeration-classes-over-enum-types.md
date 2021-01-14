---
title: Uso de las clases de enumeración en lugar de los tipos de enumeración
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Obtenga más información sobre cómo se pueden usar las clases de enumeración en lugar de las enumeraciones como una forma de resolver algunas limitaciones de estas últimas.
ms.date: 11/25/2020
ms.openlocfilehash: a45347d7cc9c3fc6378198ca1c44ba6fecfd54f5
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899533"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a>Uso de las clases de enumeración en lugar de los tipos de enumeración

Las [enumeraciones](../../../csharp/language-reference/builtin-types/enum.md) (o *tipos enum* abreviado) son un contenedor de lenguaje fino alrededor de un tipo entero. Es posible que quiera limitar su uso al momento en que almacena un valor de un conjunto cerrado de valores. La clasificación basada en tamaños (pequeño, mediano, grande) es un buen ejemplo. Usar las enumeraciones para el flujo de control o abstracciones más sólidas puede producir un [problema en el código](https://deviq.com/antipatterns/code-smells). Este tipo de uso da lugar a código frágil con muchas instrucciones de flujo de control que comprueban los valores de la enumeración.

En su lugar, puede crear clases de enumeración que habilitan todas las características enriquecidas de un lenguaje orientado a objetos.

Sin embargo, esto no es un tema crítico y, en muchos casos, por simplicidad, puede seguir usando [tipos enum](../../../csharp/language-reference/builtin-types/enum.md) normales si lo prefiere. El uso de las clases de enumeración está más relacionado con los conceptos de tipo empresarial.

## <a name="implement-an-enumeration-base-class"></a>Implementación de una clase base de enumeración

El microservicio de pedidos en eShopOnContainers proporciona una implementación de clase base de enumeración de ejemplo, como se muestra en el ejemplo siguiente:

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }

    public int Id { get; private set; }

    protected Enumeration(int id, string name) => (Id, Name) = (id, name);

    public override string ToString() => Name;

    public static IEnumerable<T> GetAll<T>() where T : Enumeration =>
        typeof(T).GetFields(BindingFlags.Public |
                            BindingFlags.Static |
                            BindingFlags.DeclaredOnly)
                 .Select(f => f.GetValue(null))
                 .Cast<T>();

    public override bool Equals(object obj)
    {
        if (obj is not Enumeration otherValue)
        {
            return false;
        }

        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);

        return typeMatches && valueMatches;
    }

    public int CompareTo(object other) => Id.CompareTo(((Enumeration)other).Id);

    // Other utility methods ...
}
```

Puede usar esta clase como un tipo en cualquier entidad u objeto de valor, como ocurre con la clase `CardType` : `Enumeration` siguiente:

```csharp
public class CardType
    : Enumeration
{
    public static CardType Amex = new CardType(1, nameof(Amex));
    public static CardType Visa = new CardType(2, nameof(Visa));
    public static CardType MasterCard = new CardType(3, nameof(MasterCard));

    public CardType(int id, string name)
        : base(id, name)
    {
    }
}
```

## <a name="additional-resources"></a>Recursos adicionales

- **Jimmy Bogard. Enumeration classes (Clases de enumeración)**  \
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- **Steve Smith. Enum Alternatives in C# (Alternativas de enumeración en C#)**  \
  <https://ardalis.com/enum-alternatives-in-c>

- **Enumeration.cs.** Base Enumeration class in eShopOnContainers (Clase base de enumeración en eShopOnContainers) \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- **CardType.cs**. Sample Enumeration class in eShopOnContainers (CardType.cs. Clase de enumeración de ejemplo en eShopOnContainers) \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>

- **SmartEnum**. Ardalis - Classes to help produce strongly typed smarter enums in .NET. (Ardalis: clases para ayudar a crear enumeraciones fuertemente tipadas de manera más inteligente en .NET) \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
>[Anterior](implement-value-objects.md)
>[Siguiente](domain-model-layer-validations.md)
