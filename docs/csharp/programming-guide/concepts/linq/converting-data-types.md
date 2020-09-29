---
title: Convertir tipos de datos (C#)
description: Los métodos de conversión cambian el tipo de los objetos de entrada. Vea operaciones de conversión en consultas de LINQ en C#, como Enumerable.AsEnumerable y Enumerable.OfType.
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: f9e3b354fd6eeba6564067550ea3821e4946d92f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159142"
---
# <a name="converting-data-types-c"></a>Convertir tipos de datos (C#)

Los métodos de conversión cambian el tipo de los objetos de entrada.

 Las operaciones de conversión en las consultas LINQ son útiles en una serie de aplicaciones. A continuación se muestran algunos ejemplos:

- El método <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> puede usarse para ocultar una implementación personalizada de tipo de un operador de consulta estándar.

- El método <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> puede usarse para permitir colecciones no parametrizadas para las consultas LINQ.

- Los métodos <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> y <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> pueden usarse para aplicar la ejecución de consultas inmediata en lugar de aplazarla hasta que se enumere la consulta.

## <a name="methods"></a>Métodos

 En la siguiente tabla se muestran los métodos de operadores de consulta estándar que efectúan conversiones de tipo de datos.

 Los métodos de conversión de esta tabla cuyos nombres comienzan por "As" cambian el tipo estático de la colección de origen, pero no lo enumeran. Los métodos cuyos nombres empiezan por "To" enumeran la colección de origen y colocan los elementos en el tipo de colección correspondiente.

|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|
|-----------------|-----------------|---------------------------------|----------------------|
|AsEnumerable|Devuelve la entrada con tipo como <xref:System.Collections.Generic.IEnumerable%601>.|No es aplicable.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|AsQueryable|Convierte un <xref:System.Collections.IEnumerable> (genérico) en un <xref:System.Linq.IQueryable> (genérico).|No es aplicable.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|Conversión de tipos explícita|Convierte los elementos de una colección en un tipo especificado.|Use una variable de rango con tipo explícito. Por ejemplo:<br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|OfType|Filtra valores en función de su capacidad para convertirse en un tipo especificado.|No es aplicable.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|ToArray|Convierte una colección en una matriz. Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|ToDictionary|Coloca elementos en <xref:System.Collections.Generic.Dictionary%602> basándose en una función de selector de claves. Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|ToList|Convierte una colección en <xref:System.Collections.Generic.List%601>. Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|ToLookup|Coloca elementos en una <xref:System.Linq.Lookup%602> (un diccionario uno a varios) basándose en una función de selector de claves. Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a>Ejemplo de sintaxis de expresiones de consulta

En el ejemplo de código siguiente se usa una variable de rango con tipo explícito para convertir un tipo en un subtipo antes de obtener acceso a un miembro que solo está disponible en el subtipo.

```csharp
class Plant
{
    public string Name { get; set; }
}

class CarnivorousPlant : Plant
{
    public string TrapType { get; set; }
}

static void Cast()
{
    Plant[] plants = new Plant[] {
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }
    };

    var query = from CarnivorousPlant cPlant in plants
                where cPlant.TrapType == "Snap Trap"
                select cPlant;

    foreach (Plant plant in query)
        Console.WriteLine(plant.Name);

    /* This code produces the following output:

        Venus Fly Trap
        Waterwheel Plant
    */
}
```

## <a name="see-also"></a>Consulte también

- <xref:System.Linq>
- [Información general sobre operadores de consulta estándar (C#)](./standard-query-operators-overview.md)
- [from (cláusula)](../../../language-reference/keywords/from-clause.md)
- [Expresiones de consulta LINQ](../../../linq/index.md)
- [Procedimiento para consultar un objeto ArrayList con LINQ (C#)](./how-to-query-an-arraylist-with-linq.md)
