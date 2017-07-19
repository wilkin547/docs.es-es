---
title: "LINQ to Entities | Microsoft Docs"
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
ms.assetid: 641f9b68-9046-47a1-abb0-1c8eaeda0e2d
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# LINQ to Entities
LINQ to Entities proporciona la capacidad de realizar consultas integradas en lenguajes \(LINQ\) que permite a los desarrolladores de software escribir consultas contra el modelo conceptual de Entity Framework mediante Visual Basic o Visual C\#.  Las consultas con Entity Framework se representan mediante consultas de árboles de comandos, que se ejecutan en el contexto del objeto.  LINQ to Entities convierte las consultas de Language\-Integrated Queries \(LINQ\) en consultas de árboles de comandos, ejecuta las consultas en Entity Framework y devuelve objetos que se pueden usar tanto en Entity Framework como en LINQ.  A continuación se muestra el proceso para crear y ejecutar una consulta de LINQ to Entities.  
  
1.  Cree una instancia de <xref:System.Data.Objects.ObjectQuery%601> en <xref:System.Data.Objects.ObjectContext>.  
  
2.  Cree una consulta de LINQ to Entities en C\# o Visual Basic con la instancia de <xref:System.Data.Objects.ObjectQuery%601>.  
  
3.  Convierta los operadores y expresiones de consulta estándar de LINQ en árboles de comandos.  
  
4.  Ejecute la consulta, con representación de un árbol de comandos, en el origen de datos.  Las excepciones producidas en el origen de datos durante la ejecución se pasan directamente al cliente.  
  
5.  Devuelva los resultados de la consulta al cliente.  
  
## Crear una instancia de ObjectQuery  
 La clase <xref:System.Data.Objects.ObjectQuery%601> genérica representa una consulta que devuelve una colección de cero o más entidades con tipo.  Una consulta de objetos se suele crear a partir de un contexto del objeto existente, en lugar de crearse de forma manual, y siempre pertenece a dicho contexto.  Este contexto proporciona la información de metadatos y de conexión necesaria para crear y ejecutar la consulta.  La clase genérica <xref:System.Data.Objects.ObjectQuery%601> implementa la interfaz genérica <xref:System.Linq.IQueryable%601>, cuyos métodos de generador permiten que las consultas de LINQ se generen de forma gradual.  También puede dejar que el compilador deduzca el tipo de entidades utilizando la palabra clave `var` de C\# \(`Dim` en Visual Basic, con la inferencia de tipos locales habilitada\).  
  
## Crear consultas  
 Las instancias de la clase genérica <xref:System.Data.Objects.ObjectQuery%601>, que implementa la interfaz genérica <xref:System.Linq.IQueryable%601>, actúan como origen de datos para las consultas de LINQ to Entities.  En una consulta se especifica exactamente la información que se desea recuperar del origen de datos.  Una consulta también puede especificar cómo se debe ordenar, agrupar y conformar esa información antes de que se devuelva.  En LINQ, una consulta se almacena en una variable.  Esta variable de consulta no realiza ninguna acción y no devuelve datos; solamente almacena la información de la consulta.  Tras crear una consulta debe ejecutarla para recuperar los datos.  
  
 Las consultas de LINQ to Entities se pueden formular en dos sintaxis diferentes: sintaxis de expresiones de consulta y sintaxis de consultas basadas en métodos.  La sintaxis de expresiones de consulta y la sintaxis de consultas basadas en métodos son una novedad de C\# 3.0 y Visual Basic 9.0.  
  
 Para obtener más información, consulta [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md).  
  
## Conversión de las consultas  
 Para ejecutar una consulta de LINQ to Entities en Entity Framework, se debe convertir a una representación de árbol de comandos que se pueda ejecutar en Entity Framework.  
  
 Las consultas de LINQ to Entities están compuestas de operadores de consulta estándar de LINQ \(como <xref:System.Linq.Queryable.Select%2A>, <xref:System.Linq.Queryable.Where%2A> y <xref:System.Linq.Queryable.GroupBy%2A>\) y expresiones \(x \> 10, Contact.LastName, etc.\).  Los operadores de LINQ no se definen en una clase, sino que son los métodos de una clase.  En LINQ, las expresiones pueden contener todo lo que permitan los tipos dentro del espacio de nombres <xref:System.Linq.Expressions> y, por extensión, todo lo que se pueda representar en una función lambda.  Se trata de un superconjunto de las expresiones permitidas por Entity Framework, que, por definición, están restringidas a las operaciones admitidas tanto en la base de datos como por <xref:System.Data.Objects.ObjectQuery%601>.  
  
 En Entity Framework, tanto los operadores como las expresiones se representan mediante una jerarquía de tipos simple, que después se coloca en un árbol de comandos.  Entity Framework usa el árbol de comandos para ejecutar la consulta.  Si la consulta de LINQ no se puede expresar como un árbol de comandos, se producirá una excepción cuando se convierta la consulta.  La conversión de las consultas de LINQ to Entities implica dos conversiones más: la de los operadores de consulta estándar y la de las expresiones.  
  
 Hay varios operadores de consulta estándar de LINQ que no tienen una conversión válida en LINQ to Entities.  Si se intenta usar estos operadores, se producirá una excepción al convertir la consulta.  Para obtener una lista de los operadores de LINQ to Entities admitidos, vea [Métodos admitidos y no admitidos de LINQ \(LINQ to Entities\)](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md).  
  
 Para obtener más información sobre cómo usar los operadores de consulta estándar en LINQ to Entities, vea [Operadores de consulta estándar en las consultas de LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/standard-query-operators-in-linq-to-entities-queries.md).  
  
 En general, las expresiones de LINQ to Entities se evalúan en el servidor, de modo que es previsible que el comportamiento de la expresión no siga la semántica de CLR.  Para obtener más información, consulta [Expresiones en consultas de LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md).  
  
 Para obtener información sobre cómo las llamadas a métodos de CLR se asignan a funciones canónicas del origen de datos, vea [Asignar método CLR a función canónica](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).  
  
 Para obtener información sobre cómo llamar a funciones canónicas, de base de datos y personalizadas desde consultas de [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], vea [Llamar a funciones en consultas de LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md).  
  
## Ejecución de la consulta  
 Una vez que el usuario crea una consulta de LINQ, esta se convierte en una representación compatible con Entity Framework \(en forma de árboles de comandos\), que después se ejecuta en el origen de datos.  En el momento de ejecutar la consulta, todas las expresiones de consulta \(o sus componentes\) se evalúan en el cliente o en el servidor.  Esto incluye las expresiones que se usan en la materialización resultante o en las proyecciones de entidades.  Para obtener más información, consulta [Ejecución de la consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md).  Para obtener información sobre cómo mejorar el rendimiento compilando una consulta una vez y ejecutándola después varias veces con parámetros diferentes, vea [Consultas compiladas \(LINQ to Entities\)](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).  
  
## Materialización  
 La materialización es el proceso por el que se devuelven los resultados de la consulta al cliente en forma de tipos de CLR.  En LINQ to Entities, los registros de datos de los resultados de las consultas no se devuelven nunca; siempre hay un tipo de CLR correspondiente, definido por el usuario o por Entity Framework, o generado por el compilador \(tipos anónimos\).  Entity Framework realiza la materialización de todos los objetos.  Los errores derivados de la incapacidad de encontrar una correspondencia entre Entity Framework y CLR hará que se produzcan excepciones durante la materialización de los objetos.  
  
 Los resultados de las consultas se suelen devolver en forma de alguno de los elementos siguientes.  
  
-   Una colección con cero o más objetos entidad con tipo o una proyección de tipos complejos que se define en el modelo conceptual.  
  
-   Tipos CLR admitidos por [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].  
  
-   Colecciones insertadas.  
  
-   Tipos anónimos.  
  
 Para obtener más información, consulta [Resultados de la consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-results.md).  
  
## En esta sección  
 [Consultas en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
  
 [Expresiones en consultas de LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)  
  
 [Llamar a funciones en consultas de LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
  
 [Consultas compiladas \(LINQ to Entities\)](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md)  
  
 [Ejecución de la consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md)  
  
 [Resultados de la consulta](../../../../../../docs/framework/data/adonet/ef/language-reference/query-results.md)  
  
 [Operadores de consulta estándar en las consultas de LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/standard-query-operators-in-linq-to-entities-queries.md)  
  
 [Asignar método CLR a función canónica](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md)  
  
 [Métodos admitidos y no admitidos de LINQ \(LINQ to Entities\)](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md)  
  
 [Problemas conocidos y consideraciones en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)  
  
## Vea también  
 [Problemas conocidos y consideraciones en LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [LINQ y ADO.NET](../../../../../../docs/framework/data/adonet/linq-and-ado-net.md)   
 [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)