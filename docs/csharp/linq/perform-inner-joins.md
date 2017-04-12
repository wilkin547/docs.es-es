---
title: Realizar combinaciones internas
description: "Cómo realizar combinaciones internas."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 45bceed6-f549-4114-a9b1-b44feb497742
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6492e536976b74fa0a0b06cdc94d8aad9584e5be
ms.lasthandoff: 03/13/2017

---
# <a name="perform-inner-joins"></a>Realizar combinaciones internas

En términos de la base de datos relacional, una *combinación interna* genera un conjunto de resultados en el que cada elemento de la primera colección aparece una vez para cada elemento coincidente en la segunda colección. Si un elemento de la primera colección no tiene ningún elemento coincidente, no aparece en el conjunto de resultados. El método <xref:System.Linq.Enumerable.Join%2A>, que se llama mediante la cláusula `join` de C#, implementa una combinación interna.  
  
 En este tema se muestra cómo realizar cuatro variaciones de una combinación interna:  
  
-   Una combinación interna simple que correlaciona elementos de dos orígenes de datos según una clave simple.  
  
-   Una combinación interna que correlaciona elementos de dos orígenes de datos según una clave *compuesta*. Una clave compuesta, que es una clave formada por más de un valor, permite correlacionar elementos en función de más de una propiedad.  
  
-   Una *combinación múltiple* en la que las sucesivas operaciones de combinación se anexan entre sí.  
  
-   Una combinación interna que se implementa mediante una combinación agrupada.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="simple-key-join-example"></a>Ejemplo de combinación de clave simple  
 En el ejemplo siguiente se crean dos colecciones que contienen objetos de dos tipos definidos por el usuario, `Person` y `Pet`. La consulta usa la cláusula `join` de C# para emparejar objetos `Person` con objetos `Pet` cuyo `Owner` sea ese `Person`. La cláusula `select` de C# define el aspecto que tendrán los objetos resultantes. En este ejemplo, los objetos resultantes son tipos anónimos que consisten en el nombre de propietario y el nombre de mascota.  
  
 [!code-cs[CsLINQProgJoining#1](../../../samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_1.cs)]  
  
 Tenga en cuenta que el objeto `Person` cuyo `LastName` es "Huff" no aparece en el conjunto de resultados porque no hay ningún objeto `Pet` que tenga `Pet.Owner` igual que `Person`.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="composite-key-join-example"></a>Ejemplo de combinación de clave compuesta  
 En lugar de correlacionar elementos en función de una sola propiedad, puede usar una clave compuesta para comparar elementos según varias propiedades. Para ello, especifique la función del selector de claves de cada colección para que devuelva un tipo anónimo que conste de las propiedades que quiere comparar. Si etiqueta las propiedades, deben tener la misma etiqueta de tipo anónimo en cada clave. Las propiedades también deben aparecer en el mismo orden.  
  
 En el ejemplo siguiente se usa una lista de objetos `Employee` y una lista de objetos `Student` para determinar qué empleados son también alumnos. Estos dos tipos tienen una propiedad `FirstName` y una propiedad `LastName` de tipo <xref:System.String>. Las funciones que crean las claves de combinación de los elementos de cada lista devuelven un tipo anónimo formado por las propiedades `FirstName` y `LastName` de cada elemento. La operación de combinación compara la igualdad de estas claves compuestas y devuelve pares de objetos de cada lista en los que el nombre y el apellido coinciden.  
  
 [!code-cs[CsLINQProgJoining#2](../../../samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_2.cs)]  
  
## <a name="example"></a>Ejemplo  
  
## <a name="multiple-join-example"></a>Ejemplo de combinación múltiple  
 Se puede anexar cualquier número de operaciones de combinación entre sí para realizar una combinación múltiple. Cada cláusula `join` de C# correlaciona un origen de datos especificado con los resultados de la combinación anterior.  
  
 En el ejemplo siguiente se crean tres colecciones: una lista de objetos `Person`, una lista de objetos `Cat` y una lista de objetos `Dog`.  
  
 La primera cláusula `join` de C# empareja personas y gatos según un objeto `Person` que coincida con `Cat.Owner`. Devuelve una secuencia de tipos anónimos que contienen el objeto `Person` y `Cat.Name`.  
  
 La segunda cláusula `join` de C# correlaciona los tipos anónimos devueltos por la primera combinación con objetos `Dog` de la lista de perros proporcionada, según una clave compuesta formada por la propiedad `Owner` de tipo `Person` y la primera letra del nombre del animal. Devuelve una secuencia de tipos anónimos que contienen las propiedades `Cat.Name` y `Dog.Name` de cada par coincidente. Como se trata de una combinación interna, solo se devuelven los objetos del primer origen de datos que tienen una correspondencia en el segundo origen de datos.  
  
 [!code-cs[CsLINQProgJoining#3](../../../samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_3.cs)]  
  
## <a name="example"></a>Ejemplo  
  
## <a name="inner-join-by-using-grouped-join-example"></a>Ejemplo de combinación interna mediante combinación agrupada  
 El ejemplo siguiente muestra cómo implementar una combinación interna mediante una combinación agrupada.  
  
 En `query1`, la lista de objetos `Person` forma una combinación agrupada con la lista de objetos `Pet` según el `Person` que coincide con la propiedad `Pet.Owner`. La combinación agrupada crea una colección de grupos intermedios, donde cada grupo consta de un objeto `Person` y una secuencia de objetos `Pet` coincidentes.  
  
 Al agregar una segunda cláusula `from` a la consulta, esta secuencia de secuencias se combina (se acopla) en una secuencia mayor. El tipo de los elementos de la secuencia final se especifica con la cláusula `select`. En este ejemplo, ese tipo es un tipo anónimo que consta de las propiedades `Person.FirstName` y `Pet.Name` de cada par coincidente.  
  
 El resultado de `query1` es equivalente al conjunto de resultados que se habría obtenido con la cláusula `join` sin la cláusula `into` para realizar una combinación interna. La variable `query2` muestra esta consulta equivalente.  
  
 [!code-cs[CsLINQProgJoining#4](../../../samples/snippets/csharp/concepts/linq/how-to-perform-inner-joins_4.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Linq.Enumerable.Join%2A>   
 <xref:System.Linq.Enumerable.GroupJoin%2A>   
 [Perform grouped joins](perform-grouped-joins.md)  (Realizar combinaciones agrupadas)  
 [Perform left outer joins](perform-left-outer-joins.md)  (Realizar operaciones de combinación externa izquierda)  
 [Anonymous types](../programming-guide/classes-and-structs/anonymous-types.md) (Tipos anónimos [Guía de programación de C#])   
 
