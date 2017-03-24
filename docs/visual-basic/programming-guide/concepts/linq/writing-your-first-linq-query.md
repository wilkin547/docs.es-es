---
title: Escribir la primera consulta LINQ (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
caps.latest.revision: 56
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 48f1c5e15654580b6e4d060860a0d7001af5e2ef
ms.lasthandoff: 03/13/2017

---
# <a name="writing-your-first-linq-query-visual-basic"></a>Escribir la primera consulta con LINQ (Visual Basic)
Un *consulta* es una expresión que recupera datos de un origen de datos. Las consultas se expresan en un lenguaje de consultas dedicado. Con el tiempo, distintos idiomas se han desarrollado para diferentes tipos de orígenes de datos, por ejemplo, SQL para bases de datos relacionales y XQuery para XML. Esto hace necesario para el desarrollador de la aplicación obtener un nuevo lenguaje de consulta para cada tipo de origen de datos o formato de datos que se admite.  
  
 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]simplifica la situación al proporcionar un modelo coherente para trabajar con datos de varios formatos y orígenes de datos. En un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consulta, siempre se trabaja con objetos. Utilice los mismos modelos de codificación básicos para consultar y transformar datos de documentos XML, bases de datos SQL, datasets de ADO.NET y entidades, las colecciones de .NET Framework y cualquier otro origen o formato para el que un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] proveedor está disponible. Este documento describe las tres fases de la creación y uso de basic [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consultas.  
  
## <a name="three-stages-of-a-query-operation"></a>Tres etapas de una operación de consulta  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]operaciones de consulta se componen de tres acciones:  
  
1.  Obtener el origen de datos o los orígenes.  
  
2.  Crear la consulta.  
  
3.  Ejecute la consulta.  
  
 En [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], la ejecución de una consulta es distinta de la creación de la consulta. No recupere los datos creando una consulta. Este punto se analiza con más detalle más adelante en este tema.  
  
 En el ejemplo siguiente se muestra las tres partes de una operación de consulta. El ejemplo utiliza una matriz de enteros como origen de datos adecuada para fines de demostración. Sin embargo, los mismos conceptos también se aplican a otros orígenes de datos.  
  
> [!NOTE]
>  En el [página compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic), asegúrese de que **Option infer** está establecido en **en**.  
  
 [!code-vb[1 VbLINQFirstQuery](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Resultado:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>El origen de datos  
 Porque el origen de datos en el ejemplo anterior es una matriz, se admite implícitamente la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>interfaz.</xref:System.Collections.Generic.IEnumerable%601> Es este hecho lo que permite utilizar una matriz como origen de datos para un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consulta. Tipos que admiten <xref:System.Collections.Generic.IEnumerable%601>o una interfaz derivada, como la genérica <xref:System.Linq.IQueryable%601>se denominan *tipos consultables*.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Como un tipo que se puede consultar implícitamente, la matriz no requiere modificaciones ni un tratamiento especial para actuar como un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] origen de datos. Lo mismo puede decirse de cualquier tipo de colección que admita <xref:System.Collections.Generic.IEnumerable%601>, incluida la interfaz genérica <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>y otras clases en la biblioteca de clases de .NET Framework.</xref:System.Collections.Generic.Dictionary%602> </xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Si los datos de origen ya no implementan <xref:System.Collections.Generic.IEnumerable%601>, un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] proveedor es necesario para implementar la funcionalidad de la *operadores de consulta estándar* para ese origen de datos.</xref:System.Collections.Generic.IEnumerable%601> Por ejemplo, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] controla el trabajo de cargar un documento XML en un consultable <xref:System.Xml.Linq.XElement>escribe, tal como se muestra en el ejemplo siguiente.</xref:System.Xml.Linq.XElement> Para obtener más información acerca de los operadores de consulta estándar, vea [Standard Query Operators Overview (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 Con [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], cree primero una asignación relacional de objetos en tiempo de diseño, ya sea manualmente o mediante el [LINQ to SQL Tools en Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) en Visual Studio. Escribir las consultas en los objetos y en tiempo de ejecución [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] administra la comunicación con la base de datos. En el ejemplo siguiente, `customers` representa una tabla específica de la base de datos y <xref:System.Data.Linq.Table%601>admite genérico <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Data.Linq.Table%601>  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Para obtener más información sobre cómo crear tipos de orígenes de datos específicos, consulte la documentación para los distintos [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] proveedores. (Para obtener una lista de estos proveedores, vea [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).) La regla básica es simple: un [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] origen de datos es cualquier objeto que admita la <xref:System.Collections.Generic.IEnumerable%601>interfaz, o una interfaz que hereda de éstos.</xref:System.Collections.Generic.IEnumerable%601>  
  
> [!NOTE]
>  Los tipos como <xref:System.Collections.ArrayList>que admiten la no genérica <xref:System.Collections.IEnumerable>interfaz también puede utilizarse como [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] orígenes de datos.</xref:System.Collections.IEnumerable> </xref:System.Collections.ArrayList> Para obtener un ejemplo que utiliza un <xref:System.Collections.ArrayList>, consulte [Cómo: consultar un objeto ArrayList con LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).</xref:System.Collections.ArrayList>  
  
## <a name="the-query"></a>La consulta  
 En la consulta, especifique qué desea recuperar desde el origen de datos o los orígenes de información. También tiene la opción de especificar cómo debe ordenada, agrupada o estructurada antes de que se devuelve esa información. Para habilitar la creación de consultas, Visual Basic incorpora nueva sintaxis de consulta en el lenguaje.  
  
 Cuando se ejecuta la consulta en el ejemplo siguiente devuelve todos los números pares de una matriz de enteros, `numbers`.  
  
 [!code-vb[1 VbLINQFirstQuery](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 La expresión de consulta contiene tres cláusulas: `From`, `Where`, y `Select`. La función específica y la finalidad de cada cláusula de expresión de consulta se analiza en [operaciones básicas de consulta (Visual Basic)](basic-query-operations.md). Para obtener más información, consulte [consultas](../../../../visual-basic/language-reference/queries/queries.md). Tenga en cuenta que en [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], una definición de consulta a menudo se almacena en una variable y ejecutarla más tarde. La consulta variable como `evensQuery` en el ejemplo anterior, debe ser un tipo consultable. El tipo de `evensQuery` es `IEnumerable(Of Integer)`, asignado por el compilador utiliza la inferencia de tipo local.  
  
 Es importante recordar que la propia variable de consulta no realiza ninguna acción y no devuelve ningún dato. Sólo almacena la definición de consulta. En el ejemplo anterior, es el `For Each` bucle que se ejecuta la consulta.  
  
## <a name="query-execution"></a>Ejecución de la consulta  
 Ejecución de la consulta es independiente de su creación. Creación de consulta define la consulta, pero la ejecución la desencadena un mecanismo diferente. Se puede ejecutar una consulta tan pronto como se define (*ejecución inmediata*), o se puede almacenar la definición y la consulta puede ejecutarse más adelante (*ejecución aplazada*).  
  
### <a name="deferred-execution"></a>Ejecución aplazada  
 Una típica [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consulta es similar a la usada en el ejemplo anterior, en el que `evensQuery` está definido. Se crea la consulta pero no la ejecuta inmediatamente. En su lugar, la definición de consulta se almacena en la variable de consulta `evensQuery`. Ejecute la consulta más adelante, normalmente mediante un `For Each` bucle, que devuelve una secuencia de valores, o aplicando un operador de consulta estándar, como `Count` o `Max`. Este proceso se conoce como *ejecución aplazada*.  
  
 [!code-vb[VbLINQFirstQuery&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Para una secuencia de valores, tener acceso a los datos recuperados mediante la variable de iteración en la `For Each` bucle (`number` en el ejemplo anterior). Dado que la variable de consulta, `evensQuery`, contiene la definición de consulta en lugar de los resultados de la consulta, puede ejecutar una consulta con tanta frecuencia como desee mediante la variable de consulta más de una vez. Por ejemplo, podría tener una base de datos en la aplicación que se está actualizando continuamente por una aplicación independiente. Después de haber creado una consulta que recupera datos de esa base de datos, puede usar un `For Each` de bucle para ejecutar la consulta de forma repetida, recuperar los datos más recientes cada vez.  
  
 En el ejemplo siguiente se muestra cómo la ejecución aplazada funciona. Después de `evensQuery2` se define y se ejecuta con un `For Each` de bucle, como en los ejemplos anteriores, algunos elementos del origen de datos `numbers` se cambian. A continuación, un segundo `For Each` bucle se ejecuta `evensQuery2` nuevo. Los resultados son diferentes la segunda vez, porque el `For Each` bucle ejecuta la consulta de nuevo, con los nuevos valores en `numbers`.  
  
 [!code-vb[VbLINQFirstQuery&3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Resultado:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Ejecución inmediata  
 Ejecución aplazada de consultas, la definición de consulta se almacena en una variable de consulta para su ejecución posterior. En la ejecución inmediata, la consulta se ejecuta en el momento de su definición. Se desencadena la ejecución cuando se aplica a un método que requiere acceso a elementos individuales del resultado de la consulta. La ejecución inmediata se fuerza mediante uno de los operadores de consulta estándar que devuelven valores únicos. Examples are `Count`, `Max`, `Average`, and `First`. Estos operadores de consulta estándar ejecutan la consulta en cuanto se aplican para calcular y devolver un resultado singleton. Para obtener más información acerca de los operadores de consulta estándar que devuelven valores únicos, vea [operaciones de agregación](aggregation-operations.md), [operaciones de elementos](element-operations.md), y [operaciones cuantificadoras](quantifier-operations.md).  
  
 La consulta siguiente devuelve un recuento de los números pares de una matriz de enteros. No se guarda la definición de consulta, y `numEvens` es un sencillo `Integer`.  
  
 [!code-vb[VbLINQFirstQuery Nº&4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 Puede conseguir el mismo resultado mediante la `Aggregate` método.  
  
 [!code-vb[VbLINQFirstQuery&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 También puede forzar la ejecución de una consulta mediante una llamada a la `ToList` o `ToArray` en una consulta (inmediata) o variable de consulta (diferida), como se muestra en el código siguiente.  
  
 [!code-vb[VbLINQFirstQuery Nº&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 En los ejemplos anteriores, `evensQuery3` es una consulta de variable, pero `evensList` es una lista y `evensArray` es una matriz.  
  
 Usando `ToList` o `ToArray` para forzar inmediatamente la ejecución es especialmente útil en escenarios en los que desea ejecutar la consulta inmediatamente y almacenar en caché los resultados en un objeto de colección único. Para obtener más información acerca de estos métodos, consulte [convertir tipos de datos](converting-data-types.md).  
  
 También puede hacer que una consulta que se ejecuta mediante el uso de un `IEnumerable` método como el <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>método.</xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A>  
  
## <a name="see-also"></a>Vea también  
 [Introducción a LINQ en Visual Basic](getting-started-with-linq.md)   
 [Inferencia de tipo local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Información general sobre operadores de consulta estándar (Visual Basic)](standard-query-operators-overview.md)   
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)
