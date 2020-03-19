---
title: Introducción a las consultas LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- deferred execution [LINQ]
- LINQ, queries
- LINQ, deferred execution
- queries [LINQ], about LINQ queries
ms.assetid: 37895c02-268c-41d5-be39-f7d936fa88a8
ms.openlocfilehash: 7fbdfa8656e3c4832226370dc6efe56964e14934
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168510"
---
# <a name="introduction-to-linq-queries-c"></a>Introducción a las consultas LINQ (C#)
Una *consulta* es una expresión que recupera datos de un origen de datos. Las consultas se suelen expresar en un lenguaje de consultas especializado. Con el tiempo se han desarrollado diferentes lenguajes para los distintos tipos de orígenes de datos, como SQL para las bases de datos relacionales y XQuery para XML. Por lo tanto, los programadores han tenido que aprender un lenguaje de consultas nuevo para cada tipo de origen de datos o formato de datos que deben admitir. LINQ simplifica esta situación al ofrecer un modelo coherente para trabajar con los datos de varios formatos y orígenes. En una consulta LINQ siempre se trabaja con objetos. Se usan los mismos patrones de codificación básicos para consultar y transformar datos de documentos XML, bases de datos SQL, conjuntos de datos de ADO.NET, colecciones de .NET y cualquier otro formato para el que haya disponible un proveedor de LINQ.  
  
## <a name="three-parts-of-a-query-operation"></a>Las tres partes de una operación de consulta  
 Todas las operaciones de consulta LINQ constan de tres acciones distintas:  
  
1. Obtener el origen de datos.  
  
2. Crear la consulta.  
  
3. Ejecutar la consulta.  
  
 En el siguiente ejemplo se muestra cómo se expresan las tres partes de una operación de consulta en código fuente. En el ejemplo se usa una matriz de enteros como origen de datos para su comodidad, aunque se aplican los mismos conceptos a otros orígenes de datos. En el resto de este tema se hará referencia a este ejemplo.  
  
 [!code-csharp[CsLINQGettingStarted#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#1)]  
  
 En la siguiente ilustración se muestra toda la operación de consulta. En LINQ, la ejecución de la consulta es distinta de la propia consulta. En otras palabras, no ha recuperado ningún dato simplemente creando una variable de consulta.  
  
 ![Diagrama de la operación de consulta LINQ completa.](./media/introduction-to-linq-queries/linq-query-complete-operation.png)  
  
## <a name="the-data-source"></a>El origen de datos  
 En el ejemplo anterior, como el origen de datos es una matriz, admite implícitamente la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>. Este hecho implica que se puede consultar con LINQ. Se ejecuta una consulta en una instrucción `foreach`, y `foreach` requiere <xref:System.Collections.IEnumerable> o bien <xref:System.Collections.Generic.IEnumerable%601>. Los tipos compatibles con <xref:System.Collections.Generic.IEnumerable%601> o una interfaz derivada, como la interfaz genérica <xref:System.Linq.IQueryable%601>, se denominan *tipos consultables*.  
  
 Un tipo consultable no requiere ninguna modificación ni ningún tratamiento especial para actuar como origen de datos de LINQ. Si el origen de datos no está en la memoria como tipo consultable, el proveedor de LINQ debe representarlo como tal. Por ejemplo, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] carga un documento XML en un tipo <xref:System.Xml.Linq.XElement> consultable:  
  
 [!code-csharp[CsLINQGettingStarted#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#2)]  
  
 Con [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], primero se crea una asignación relacional de objetos en tiempo de diseño ya sea manualmente o mediante las [herramientas de LINQ to SQL](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) de Visual Studio. Después, se escriben las consultas en los objetos y, en tiempo de ejecución, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] controla la comunicación con la base de datos. En el ejemplo siguiente, `Customers` representa una tabla específica en una base de datos, y el tipo del resultado de la consulta, <xref:System.Linq.IQueryable%601>, se deriva de <xref:System.Collections.Generic.IEnumerable%601>.  
  
```csharp  
Northwnd db = new Northwnd(@"c:\northwnd.mdf");  
  
// Query for customers in London.  
IQueryable<Customer> custQuery =  
    from cust in db.Customers  
    where cust.City == "London"  
    select cust;  
```  
  
 Para obtener más información sobre cómo crear tipos específicos de orígenes de datos, consulte la documentación de los distintos proveedores de LINQ. Aun así, la regla básica es muy sencilla: un origen de datos de LINQ es cualquier objeto que admita la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601> o una interfaz que la haya heredado.  
  
> [!NOTE]
> Los tipos como <xref:System.Collections.ArrayList>, que admiten la interfaz no genérica <xref:System.Collections.IEnumerable>, también se pueden usar como origen de datos de LINQ. Para más información, consulte el [procedimiento para consultar un objeto ArrayList con LINQ (C#)](./how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a><a name="query"></a> La consulta  
 La consulta especifica la información que se debe recuperar de los orígenes de datos. Opcionalmente, una consulta también especifica cómo se debe ordenar, agrupar y conformar esa información antes de que se devuelva. Las consultas se almacenan en una variable de consulta y se inicializan con una expresión de consulta. Para facilitar la escritura de consultas, C# ha incorporado una nueva sintaxis de consulta.  
  
 La consulta del ejemplo anterior devuelve todos los números pares de la matriz de enteros. La expresión de consulta contiene tres cláusulas: `from`, `where` y `select` (si está familiarizado con SQL, habrá observado que el orden de las cláusulas se invierte respecto al orden de SQL). La cláusula `from` especifica el origen de datos, la cláusula `where` aplica el filtro y la cláusula `select` especifica el tipo de los elementos devueltos. Estas y otras cláusulas de consulta se tratan con detalle en la sección [Language Integrated Query (LINQ)](../../../linq/index.md). Por ahora, lo importante es que en LINQ la variable de consulta no efectúa ninguna acción y no devuelve ningún dato. Lo único que hace es almacenar la información necesaria para generar los resultados cuando se ejecuta la consulta en algún momento posterior. Para obtener más información sobre cómo se construyen las consultas en segundo plano, vea [Información general sobre operadores de consulta estándar (C#)](./standard-query-operators-overview.md).  
  
> [!NOTE]
> Las consultas también se pueden expresar empleando una sintaxis de método. Para obtener más información, vea [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md) (Sintaxis de consulta y sintaxis de método en LINQ).  
  
## <a name="query-execution"></a>Ejecución de la consulta  
  
### <a name="deferred-execution"></a>Ejecución aplazada  
 Como se ha indicado anteriormente, la variable de consulta solo almacena los comandos de consulta. La ejecución real de la consulta se aplaza hasta que se procese una iteración en la variable de consulta en una instrucción `foreach`. Este concepto se conoce como *ejecución aplazada* y se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csLinqGettingStarted#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#4)]  
  
 La instrucción `foreach` es también donde se recuperan los resultados de la consulta. Por ejemplo, en la consulta anterior, la variable de iteración `num` contiene cada valor (de uno en uno) en la secuencia devuelta.  
  
 Dado que la propia variable de consulta nunca contiene los resultados de la consulta, puede ejecutarla tantas veces como desee. Por ejemplo, se puede tener una base de datos que esté siendo actualizada de forma continua por otra aplicación. En su aplicación, se puede crear una consulta que recupere los datos más recientes y se puede ejecutar repetidamente de acuerdo con un intervalo para recuperar resultados diferentes cada vez.  
  
### <a name="forcing-immediate-execution"></a>Forzar la ejecución inmediata  
 Las consultas que llevan a cabo funciones de agregación en un intervalo de elementos de origen primero deben recorrer en iteración dichos elementos. Ejemplos de estas consultas son `Count`, `Max`, `Average` y `First`. Se ejecutan sin una instrucción `foreach` explícita, ya que la propia consulta debe usar `foreach` para poder devolver un resultado. Tenga en cuenta también que estos tipos de consultas devuelven un único valor, y no una colección `IEnumerable`. La consulta siguiente devuelve un recuento de los números pares de la matriz de origen:  
  
 [!code-csharp[csLinqGettingStarted#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#5)]  
  
 Para forzar la ejecución inmediata de cualquier consulta y almacenar en caché los resultados correspondientes, puede llamar a los métodos <xref:System.Linq.Enumerable.ToList%2A> o <xref:System.Linq.Enumerable.ToArray%2A>.  
  
 [!code-csharp[csLinqGettingStarted#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#6)]  
  
 También puede forzar la ejecución colocando el bucle `foreach` justo después de la expresión de consulta, aunque, si se llama a `ToList` o a `ToArray`, también se almacenan en caché todos los datos de un objeto de colección.  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en C#](index.md)
- [Tutorial: Escribir consultas en C#](./walkthrough-writing-queries-linq.md)
- [Language-Integrated Query (LINQ)](../../../linq/index.md)
- [foreach, in](../../../language-reference/keywords/foreach-in.md)
- [Palabras clave para consultas (LINQ)](../../../language-reference/keywords/query-keywords.md)
