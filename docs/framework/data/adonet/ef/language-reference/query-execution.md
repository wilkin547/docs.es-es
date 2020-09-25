---
title: Ejecución de la consulta
description: Obtenga información sobre las distintas formas en que se ejecuta una consulta LINQ to Entities, incluida la ejecución diferida de consultas, la ejecución inmediata de consultas y la ejecución de la tienda.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c0e6cf23-63ac-47dd-bfe9-d5bdca826fac
ms.openlocfilehash: e5961330eab5f25508319f276df1e9b4572f49ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189310"
---
# <a name="query-execution"></a>Ejecución de la consulta

Una vez creada por un usuario una consulta LINQ, se convierte en un árbol de comandos. Un árbol de comandos es una representación de una consulta que es compatible con Entity Framework. Posteriormente, el árbol de comandos se ejecuta en el origen de datos. En el momento de la ejecución de la consulta, se evalúan todas las expresiones de consulta (es decir, todos los componentes de la consulta), incluidas las expresiones que se utilizan en la materialización del resultado.  
  
 El momento en que se ejecutan las expresiones de consulta puede variar. Las consultas LINQ siempre se ejecutan cuando se recorre en iteración la variable de consulta, no cuando se crea la citada variable de consulta. Esto se denomina *ejecución aplazada*. También se puede obligar a que la consulta se ejecute inmediatamente, lo que es útil para almacenar en caché los resultados de la consulta. Esto se describe más adelante en este tema.  
  
 Cuando se ejecuta una consulta de LINQ to Entities, algunas de sus expresiones podrían ejecutarse en el servidor y ciertas partes podrían ejecutarse de forma local en el cliente. La evaluación en el cliente de una expresión se lleva a cabo antes de ejecutar la consulta en el servidor. Si una expresión se evalúa en el cliente, el resultado de esa evaluación se sustituye por la expresión en la consulta, y ésta se ejecuta entonces en el servidor. Dado que las consultas se ejecutan en el origen de datos, la configuración de este reemplaza el comportamiento especificado en el cliente. Por ejemplo, la precisión numérica y el tratamiento de los valores NULL dependen de la configuración de servidor. Cualquier excepción que se produzca durante la ejecución de la consulta en el servidor se pasa directamente al cliente.  

> [!TIP]
> Para obtener un breve resumen de los operadores de consulta en formato de tabla, lo que permite identificar rápidamente el comportamiento de ejecución de un operador, vea [clasificación de operadores de consulta estándar por modo de ejecución (C#)](../../../../../csharp/programming-guide/concepts/linq/classification-of-standard-query-operators-by-manner-of-execution.md).

## <a name="deferred-query-execution"></a>Ejecución de consultas en diferido  

 En una consulta que devuelve una secuencia de valores, la variable de consulta por sí misma nunca conserva los resultados de la consulta y solo almacena los comandos de la misma. La ejecución de la consulta se aplaza hasta que la variable de consulta se recorre en iteración en un bucle `foreach` o `For Each`. Esto se conoce como *ejecución aplazada*; es decir, la ejecución de la consulta se produce una vez después de la construcción de la consulta. Esto significa que se puede ejecutar una consulta con la frecuencia que se desee. Esto es útil cuando, por ejemplo, se tiene una base de datos que otras aplicaciones están actualizando. En su aplicación puede crear una consulta para recuperar la información más reciente y ejecutar de forma repetida la consulta, devolviendo cada vez la información actualizada.  
  
 La ejecución aplazada permite combinar varias consultas o ampliar una consulta. Cuando se amplía una consulta, se modifica para incluir las nuevas operaciones. La ejecución eventual reflejará los cambios. En el siguiente ejemplo, la primera consulta devuelve todos los productos. La segunda consulta amplía la primera usando `Where` para devolver todos los productos del tamaño "L":  
  
 [!code-csharp[DP L2E Conceptual Examples#Composing1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#composing1)]
 [!code-vb[DP L2E Conceptual Examples#Composing1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#composing1)]  
  
 Una vez ejecutada una consulta, todas las consultas sucesivas utilizarán los operadores de LINQ en memoria. Si se recorre en iteración la variable de la consulta utilizando una instrucción `foreach` o `For Each` o llamando a uno de los operadores de conversión de LINQ, se producirá la ejecución inmediata. Entre estos operadores de conversión se incluyen los siguientes: <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToLookup%2A> y <xref:System.Linq.Enumerable.ToDictionary%2A>.  
  
## <a name="immediate-query-execution"></a>Ejecución de consultas inmediata  

 A diferencia de la ejecución aplazada de consultas que producen una secuencia de valores, las consultas que devuelven un valor singleton se ejecutan inmediatamente. Algunos ejemplos de consultas singleton son <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.First%2A> y <xref:System.Linq.Enumerable.Max%2A>. Se ejecutan inmediatamente porque la consulta debe producir una secuencia para calcular el resultado singleton. También se puede forzar la ejecución inmediata. Esto es útil cuando se desea almacenar en memoria caché los resultados de una consulta. Para forzar la ejecución inmediata de una consulta que no produce un valor singleton, se puede llamar a los métodos <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> o <xref:System.Linq.Enumerable.ToArray%2A> en una consulta o una variable de consulta. En el ejemplo siguiente se utiliza el método <xref:System.Linq.Enumerable.ToArray%2A> para evaluar de forma inmediata una secuencia en una matriz.  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
 También se puede forzar la ejecución colocando el bucle `foreach` o `For Each` inmediatamente después de la expresión de consulta, pero si se llama a los métodos <xref:System.Linq.Enumerable.ToList%2A> o <xref:System.Linq.Enumerable.ToArray%2A>, se almacenarán en caché todos los datos de un solo objeto de la colección.  
  
## <a name="store-execution"></a>Ejecución en el almacén  

 En general, las expresiones de LINQ to Entities se evalúan en el servidor, y no es de esperar que el comportamiento de la expresión siga la semántica de Common Language Runtime (CLR), sino la del origen. Sin embargo, hay excepciones, como cuando la expresión se ejecuta en el cliente. Esto puede producir resultados inesperados, por ejemplo cuando el servidor y el cliente están en zonas horarias diferentes.  
  
 Algunas expresiones de la consulta se pueden ejecutar en el cliente. En general, se espera que la mayor parte de la ejecución de la consulta se produzca en el servidor. Además de los métodos ejecutados en elementos de consulta asignados al origen de datos, suele haber expresiones de la consulta que se pueden ejecutar localmente. La ejecución local de una expresión de consulta produce un valor que se puede utilizar en la ejecución de la consulta o en la generación del resultado.  
  
 Ciertas operaciones se ejecutan siempre en el cliente, como el enlace de valores, subexpresiones, subconsultas de cierres, y la materialización de objetos en los resultados de la consulta. La consecuencia final es que estos elementos (por ejemplo, los valores de parámetro) no se pueden actualizar durante la ejecución. Los tipos anónimos se pueden crear alineados en el origen de datos, pero no se debe suponer que esto se vaya a producir. Las agrupaciones alineadas también se pueden crear en el almacén, pero no se debe suponer que esto tenga lugar en cada instancia. En general, es preferible no hacer suposiciones sobre lo que se crea en el servidor.  
  
 En esta sección se describen los escenarios en que el código se ejecuta localmente en el cliente. Para obtener más información sobre los tipos de expresiones que se ejecutan localmente, vea [expresiones en consultas de LINQ to Entities](expressions-in-linq-to-entities-queries.md).  
  
### <a name="literals-and-parameters"></a>Literales y parámetros  

 Las variables locales, como la variable `orderID` del ejemplo siguiente, se evalúan en el cliente.  
  
 [!code-csharp[DP L2E Conceptual Examples#LiteralParameter1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#literalparameter1)]
 [!code-vb[DP L2E Conceptual Examples#LiteralParameter1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#literalparameter1)]  
  
 Los parámetros de métodos también se evalúan en el cliente. El parámetro `orderID` que se pasa al método `MethodParameterExample`, como se puede apreciar más abajo, es un ejemplo.  
  
 [!code-csharp[DP L2E Conceptual Examples#MethodParameterExample](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#methodparameterexample)]
 [!code-vb[DP L2E Conceptual Examples#MethodParameterExample](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#methodparameterexample)]  
  
### <a name="casting-literals-on-the-client"></a>Convertir literales en el cliente  

 La conversión de `null` a un tipo CLR se ejecuta en el cliente:  
  
 [!code-csharp[DP L2E Conceptual Examples#NullCastToString](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#nullcasttostring)]
 [!code-vb[DP L2E Conceptual Examples#NullCastToString](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#nullcasttostring)]  
  
 La conversión a un tipo, como un <xref:System.Decimal> que acepta valores NULL, se ejecuta en el cliente:  
  
 [!code-csharp[DP L2E Conceptual Examples#CastToNullable](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#casttonullable)]
 [!code-vb[DP L2E Conceptual Examples#CastToNullable](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#casttonullable)]  
  
### <a name="constructors-for-literals"></a>Constructores para literales  

 Los nuevos tipos CLR que se pueden asignar a tipos del modelo conceptual se ejecutan en el cliente:  
  
 [!code-csharp[DP L2E Conceptual Examples#ConstructorForLiteral](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#constructorforliteral)]
 [!code-vb[DP L2E Conceptual Examples#ConstructorForLiteral](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#constructorforliteral)]  
  
 Las nuevas matrices también se ejecutan en el cliente.  
  
## <a name="store-exceptions"></a>Excepciones en el almacén  

 Los errores en el almacén que tienen lugar durante la ejecución de la consulta se pasan al cliente y no se asignan ni controlan.  
  
## <a name="store-configuration"></a>Configuración del almacén  

 Cuando la consulta se ejecuta en el almacén, la configuración del almacén invalida todos los comportamientos del cliente, y la semántica del almacén se expresa para todas las operaciones y expresiones. El resultado puede ser una diferencia de comportamiento entre la ejecución en el CLR y la ejecución en el almacén en áreas como las comparaciones de NULL, la ordenación de GUID, la precisión y la exactitud de las operaciones que afectan a tipos de datos no precisos (como los tipos de punto flotante o <xref:System.DateTime>) y las operaciones de cadena. Es importante tener esto en cuenta al examinar los resultados de la consulta.  
  
 Por ejemplo, a continuación se indican algunas diferencias de comportamiento entre CLR y SQL Server:  
  
- SQL Server ordena los GUID de manera diferente que CLR.  
  
- También puede haber diferencias en la precisión del resultado cuando se trabaja con el tipo Decimal en SQL Server. Esto se debe a los requisitos de precisión fijados para el tipo decimal de SQL Server. Por ejemplo, el valor medio de los valores <xref:System.Decimal> 0.0, 0.0, y 1.0 es 0.3333333333333333333333333333 en memoria en el cliente, pero 0.333333 en el almacén (si se toma como base la precisión predeterminada para el tipo decimal de SQL Server).  
  
- Algunas operaciones de comparación de cadenas también se tratan en SQL Server de forma diferente que en CLR. El comportamiento de la comparación de cadenas depende de los valores de intercalación en el servidor.  
  
- Las llamadas a funciones o métodos, cuando se incluyen en una consulta de LINQ to Entities, se asignan a funciones canónicas en Entity Framework, que, posteriormente, se convierten a Transact-SQL y se ejecutan en la base de datos de SQL Server. Hay casos en que el comportamiento que muestran estas funciones asignadas puede diferir de la implementación en las bibliotecas de clases base. Por ejemplo, una llamada a los métodos <xref:System.String.Contains%2A>, <xref:System.String.StartsWith%2A> y <xref:System.String.EndsWith%2A> con una cadena vacía como parámetro, devolverá `true` si se ejecuta en CLR pero devolverá `false` si se ejecuta en SQL Server. El método <xref:System.String.EndsWith%2A> también puede devolver resultados diferentes porque SQL Server considera que dos cadenas son iguales si solo se diferencian en el espacio en blanco final, mientras que CLR considera que no son iguales. Esto se muestra en el ejemplo siguiente:  
  
 [!code-csharp[DP L2E Conceptual Examples#CanonicalFuncVsCLRBaseType](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#canonicalfuncvsclrbasetype)]
 [!code-vb[DP L2E Conceptual Examples#CanonicalFuncVsCLRBaseType](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#canonicalfuncvsclrbasetype)]
