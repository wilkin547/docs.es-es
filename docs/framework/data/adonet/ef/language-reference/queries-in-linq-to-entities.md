---
title: "Consultas en LINQ to Entities | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Consultas en LINQ to Entities
Una consulta es una expresión que recupera datos de un origen de datos.  Las consultas se suelen expresar en un lenguaje de consulta especializado, como SQL para bases de datos relacionales y XQuery para XML.  Por lo tanto, los programadores han tenido que aprender un lenguaje de consultas nuevo para cada tipo de origen de datos o formato de datos que consultan.  Language\-Integrated Query \(LINQ\) ofrece un modelo coherente y más sencillo para trabajar con los datos de varios formatos y orígenes de datos.  En una consulta de LINQ siempre se trabaja con objetos de programación.  
  
 Una operación de consulta de LINQ consta de tres acciones: obtener el origen o los orígenes de datos, crear la consulta y ejecutar la consulta.  
  
 Los orígenes de datos que implementan las interfaces genéricas <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601> pueden consultarse a través de LINQ.  Las instancias de la clase genérica <xref:System.Data.Objects.ObjectQuery%601>, que implementa la interfaz genérica <xref:System.Linq.IQueryable%601>, actúan como origen de datos para las consultas [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  La clase <xref:System.Data.Objects.ObjectQuery%601> genérica representa una consulta que devuelve una colección de cero o más objetos con tipo.  También puede hacer que el compilador deduzca el tipo de una entidad utilizando la palabra clave `var` de C\# \(Dim en Visual Basic\).  
  
 En la consulta se especifica exactamente la información que se desea recuperar del origen de datos.  Una consulta también puede especificar cómo se debe ordenar, agrupar y conformar esa información antes de que se devuelva.  En LINQ, una consulta se almacena en una variable.  Si la consulta devuelve una secuencia de valores, la propia variable de la consulta debe ser de un tipo que se pueda consultar.  Esta variable de consulta no realiza ninguna acción y no devuelve datos; solamente almacena la información de la consulta.  Tras crear una consulta debe ejecutarla para recuperar los datos.  
  
## Sintaxis de consulta  
 Las consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] se pueden formular en dos sintaxis diferentes: sintaxis de expresiones de consulta y sintaxis de consultas basadas en métodos.  La sintaxis de expresiones de consulta es nueva en C\# 3.0 y Visual Basic 9.0, y consta de un conjunto de cláusulas escritas en una sintaxis declarativa similar a Transact\-SQL o XQuery.  No obstante, Common Language Runtime \(CLR\) de [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] no puede leer la sintaxis de expresiones de consulta en sí.  Por lo tanto, en tiempo de compilación, las expresiones de consulta se traducen a algo que CLR no comprende: las llamadas a métodos.  Esos métodos se conocen como *operadores de consulta estándar*.  Como programador, tiene la opción de llamarlos directamente utilizando la sintaxis de método en lugar de la sintaxis de consulta. Para obtener más información, consulte [Query Syntax and Method Syntax in LINQ](../Topic/Query%20Syntax%20and%20Method%20Syntax%20in%20LINQ%20\(C%23\).md).  
  
### Sintaxis de expresiones de consulta  
 Las expresiones de consulta son una sintaxis de consulta declarativa.  Esta sintaxis permite a un programador escribir consultas en un lenguaje de alto nivel que tenga un formato similar al de Transact\-SQL.  Si se utiliza la sintaxis de expresiones de consulta, se pueden realizar incluso operaciones complejas de filtrado, ordenación y agrupamiento en orígenes de datos con código mínimo.  Para obtener más información, consulte [Operaciones básicas de consulta \(Visual Basic\)](../Topic/Basic%20Query%20Operations%20\(Visual%20Basic\).md).  Para obtener ejemplos que muestran cómo utilizar la sintaxis de expresiones de consulta, vea los siguientes temas:  
  
-   [Ejemplos de sintaxis de expresiones de consulta: proyección](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-projection.md)  
  
-   [Ejemplos de sintaxis de expresión de consultas: filtrado](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-filtering.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: ordenación](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-ordering.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: operadores de agregado](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: creación de particiones](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-partitioning.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: operadores de combinación](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-join-operators.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: operadores de elementos](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-element-operators.md)  
  
-   [Ejemplos de sintaxis de expresiones de consulta: agrupamiento](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-grouping.md)  
  
-   [Ejemplos de sintaxis de expresiones de consultas: navegar por relaciones](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-navigating-relationships.md)  
  
### Sintaxis de consultas basadas en métodos  
 Otra forma de formular consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] es usar las consultas basadas en métodos.  La sintaxis de consultas basadas en métodos es una secuencia de llamadas directas a los métodos de operador de LINQ que pasan expresiones lambda como parámetros.  Para obtener más información, consulte [Expresiones lambda](../Topic/Lambda%20Expressions%20\(C%23%20Programming%20Guide\).md).  Para obtener ejemplos que muestran cómo utilizar la sintaxis basada en métodos, vea los siguientes temas:  
  
-   [Ejemplos de sintaxis de consulta basada en métodos: proyección](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-projection.md)  
  
-   [Ejemplos de sintaxis de consulta basada en métodos: Filtrado](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-filtering.md)  
  
-   [Ejemplos de sintaxis de consulta basada en métodos: ordenación](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-ordering.md)  
  
-   [Ejemplos de sintaxis de consulta basada en métodos: operadores de agregado](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [Ejemplos de sintaxis de consulta basada en métodos: creación de particiones](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-partitioning.md)  
  
-   [Ejemplos de sintaxis de consulta basada en métodos: conversión](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-conversion.md)  
  
-   [Ejemplos de sintaxis de consulta basada en métodos: operadores de combinación](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-join-operators.md)  
  
-   [Ejemplos de sintaxis de consulta basada en métodos: operadores de elementos](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-element-operators.md)  
  
-   [Ejemplos de sintaxis de consulta basada en métodos: Agrupación](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-grouping.md)  
  
-   [Ejemplos de sintaxis de consulta basada en métodos: navegar por relaciones](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-navigating-relationships.md)  
  
## Vea también  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)   
 [Getting Started with LINQ in C\#](../Topic/Getting%20Started%20with%20LINQ%20in%20C%23.md)   
 [Getting Started with LINQ in Visual Basic](../Topic/Getting%20Started%20with%20LINQ%20in%20Visual%20Basic.md)   
 [Opciones de combinación de Entity Framework y consultas compiladas](http://go.microsoft.com/fwlink/?LinkId=199591)