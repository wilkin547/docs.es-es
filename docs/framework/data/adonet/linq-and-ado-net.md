---
title: LINQ y ADO.NET
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: a23e152d4688e840f4665e9c8d77835acb683564
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307317"
---
# <a name="linq-and-adonet"></a>LINQ y ADO.NET
En la actualidad, muchos programadores empresariales deben usar dos (o más) lenguajes de programación: un lenguaje de alto nivel para las capas de presentación y lógica de negocios (por ejemplo, Visual C# o Visual Basic) y un lenguaje de consulta para interactuar con la base de datos (por ejemplo, Transact-SQL) . Esto requiere que el programador tenga conocimientos de varios idiomas para ser efectivo y también causa discrepancias de idiomas en el entorno de desarrollo. Por ejemplo, una aplicación que utiliza API de acceso a datos para ejecutar una consulta en una base de datos especifica la consulta como un literal de cadena usando comillas. Esta cadena de consulta es ilegible y no se comprueba si contiene errores, tales como una sintaxis no válida o si existen las columnas o las filas a las que hace referencia. No hay ninguna comprobación de tipo de los parámetros de consulta y tampoco hay compatibilidad con `IntelliSense`.  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] permite a los programadores formar consultas basadas en conjuntos en el código de su aplicación, sin tener que usar un lenguaje de consulta independiente. Se puede escribir consultas de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] en varios orígenes de datos enumerables (es decir, un origen de datos que implementa la interfaz <xref:System.Collections.IEnumerable>), como estructuras de datos en memoria, documentos XML, bases de datos SQL y objetos <xref:System.Data.DataSet>. Aunque esos orígenes de datos enumerables se implementan de varias formas, todos revelan las mismas construcciones de lenguaje y sintaxis. Como las consultas se pueden formar en el lenguaje de programación mismo, no es necesario utilizar otro lenguaje de consultas que esté incrustado como literales de cadena que el compilador no pueda entender o comprobar. Integración de las consultas en el lenguaje de programación también permite a los programadores de Visual Studio sean más productivos proporcionando comprobación de sintaxis y tipo en tiempo de compilación y `IntelliSense`. Estas características reducen la necesidad de depuración y corrección de errores de consultas.  
  
 La transferencia de datos de las tablas de SQL a objetos de memoria a menudo es una tarea tediosa y propensa a errores. El proveedor de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] implementado por [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] y [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] convierte el origen de datos en recopilaciones de objetos basadas en <xref:System.Collections.IEnumerable>. El programador siempre ve los datos como una colección de <xref:System.Collections.IEnumerable> cuando se realiza la consulta y la actualización. Se proporciona compatibilidad completa con `IntelliSense` para escribir consultas en esas colecciones.  
  
 Existen tres tecnologías [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] de ADO.NET independientes: [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] y [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Proporciona consultas más enriquecidas y optimizadas a través de la <xref:System.Data.DataSet> y [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] le permite consultar directamente esquemas de base de datos de SQL Server, y [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] le permite consultar un Entity Data Model.  
  
 El siguiente diagrama proporciona una visión general de cómo se relacionan las tecnologías ADO.NET LINQ con lenguajes de programación de alto nivel y orígenes de datos habilitados para LINQ.  
  
 ![Información general ADO.NET LINQ to](../../../../docs/framework/data/adonet/media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 Para obtener más información acerca de LINQ, vea [Language Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).
  
 En las siguientes secciones se proporciona más información acerca de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] y [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 El <xref:System.Data.DataSet> es un elemento fundamental del modelo de programación desconectado que se basa en ADO.NET y se usa ampliamente. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] permite a los programadores crear capacidades de consulta más complejas en <xref:System.Data.DataSet> utilizando el mismo mecanismo de formulación de consultas que está disponible para muchos otros orígenes de datos. Para más información, vea [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] es una herramienta útil para programadores que no requieren la asignación a un modelo conceptual. Si utiliza [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], puede usar el modelo de programación de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] directamente en un esquema de base de datos existente. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] permite a los programadores generar clases de .NET Framework que representan datos. En lugar de la asignación a un modelo de datos conceptual, esas clases generadas se asignan directamente a tablas de bases de datos, vistas, procedimientos almacenados y funciones definidas por el usuario.  
  
 Con [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], los programadores pueden escribir código directamente en el esquema de almacenamiento usando el mismo patrón de programación de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] que las recopilaciones en memoria y <xref:System.Data.DataSet>, además de otros orígenes de datos como XML. Para más información, vea [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 La mayor parte de las aplicaciones se escriben actualmente utilizando bases de datos relacionales. En algún punto, estas aplicaciones tendrán que interactuar con los datos representados en un formato relacional. Los esquemas de base de datos no siempre son ideales para crear aplicaciones y los modelos conceptuales de aplicación no son iguales que los modelos lógicos de bases de datos. El Entity Data Model es un modelo de datos conceptual que se puede usar para modelar los datos de un dominio en particular para que las aplicaciones puedan interactuar con datos como objetos. Consulte [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) para obtener más información.  
  
 A través de Entity Data Model, datos relacionales se exponen como objetos en el entorno. NET. Esto hace de la capa de objetos un objetivo idóneo para la compatibilidad con [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], ya que permite a los programadores formular consultas en la base de datos con el lenguaje usado para compilar la lógica empresarial. Esta función se conoce como [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]. Para más información, vea [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vea también

- [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)
- [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)
- [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
- [Language-Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
