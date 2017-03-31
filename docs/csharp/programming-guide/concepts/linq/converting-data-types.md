---
title: Convertir tipos de datos (C#) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 922e2f26c5f8ded260644e8effa043b03b721020
ms.lasthandoff: 03/13/2017

---
# <a name="converting-data-types-c"></a>Convertir tipos de datos (C#)
Los métodos de conversión cambian el tipo de los objetos de entrada.  
  
 Las operaciones de conversión en las consultas LINQ son útiles en una serie de aplicaciones. A continuación se muestran algunos ejemplos:  
  
-   El método <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> se puede usar para ocultar la implementación personalizada de un tipo de un operador de consulta estándar.  
  
-   El método <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> se puede usar para habilitar las colecciones no parametrizadas para efectuar consultas LINQ.  
  
-   Los métodos <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> y <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> se pueden usar para forzar la ejecución inmediata de la consulta en lugar de aplazarla hasta que se haya enumerado la consulta.  
  
## <a name="methods"></a>Métodos  
 En la siguiente tabla se muestran los métodos de operadores de consulta estándar que efectúan conversiones de tipo de datos.  
  
 Los métodos de conversión de esta tabla cuyos nombres comienzan por "As" cambian el tipo estático de la colección de origen, pero no lo enumeran. Los métodos cuyos nombres empiezan por "To" enumeran la colección de origen y colocan los elementos en el tipo de colección correspondiente.  
  
|Nombre del método|Descripción|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|AsEnumerable|Devuelve la entrada tipificada como <xref:System.Collections.Generic.IEnumerable%601>.|No es aplicable.|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>|  
|AsQueryable|Convierte <xref:System.Collections.IEnumerable> (genérico) en <xref:System.Linq.IQueryable> (genérico).|No es aplicable.|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>|  
|Conversión de tipos explícita|Convierte los elementos de una colección en un tipo especificado.|Use una variable de rango con tipo explícito. Por ejemplo:<br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName>|  
|OfType|Filtra valores en función de su capacidad para convertirse en un tipo especificado.|No es aplicable.|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName>|  
|ToArray|Convierte una colección en una matriz. Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>|  
|ToDictionary|Coloca los elementos en un <xref:System.Collections.Generic.Dictionary%602> a partir de una función del selector de claves. Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>|  
|ToList|Convierte una colección en una <xref:System.Collections.Generic.List%601>. Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>|  
|ToLookup|Coloca los elementos en <xref:System.Linq.Lookup%602> (diccionario uno a varios) según una función del selector de claves. Este método fuerza la ejecución de la consulta.|No es aplicable.|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>|  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq>   
 [Información general sobre operadores de consulta estándar (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [from (Cláusula)](../../../../csharp/language-reference/keywords/from-clause.md)   
 [Expresiones de consulta LINQ](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [How to: Query an ArrayList with LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md) (Cómo: Consultar un objeto ArrayList con LINQ (C#))
