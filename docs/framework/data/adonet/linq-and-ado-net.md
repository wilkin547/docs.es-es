---
title: LINQ y ADO.NET
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: 1385b2d9b49a7615810025141e111b7d7bf71eac
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="linq-and-adonet"></a>LINQ y ADO.NET
Hoy en día, muchos programadores empresariales deben usar dos (o más) lenguajes de programación: un lenguaje de alto nivel para las capas de presentación y lógica de negocios (por ejemplo, Visual C# o Visual Basic) y un lenguaje de consulta para interactuar con la base de datos (como [!INCLUDE[tsql](../../../../includes/tsql-md.md)]). Esto requiere que el programador tenga conocimientos de varios idiomas para ser efectivo y también causa discrepancias de idiomas en el entorno de desarrollo. Por ejemplo, una aplicación que utiliza API de acceso a datos para ejecutar una consulta en una base de datos especifica la consulta como un literal de cadena usando comillas. Esta cadena de consulta es ilegible y no se comprueba si contiene errores, tales como una sintaxis no válida o si existen las columnas o las filas a las que hace referencia. No hay ninguna comprobación de tipo de los parámetros de consulta y tampoco hay compatibilidad con `IntelliSense`.  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] permite a los programadores formar consultas basadas en conjuntos en el código de su aplicación, sin tener que usar un lenguaje de consulta independiente. Se puede escribir consultas de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] en varios orígenes de datos enumerables (es decir, un origen de datos que implementa la interfaz <xref:System.Collections.IEnumerable>), como estructuras de datos en memoria, documentos XML, bases de datos SQL y objetos <xref:System.Data.DataSet>. Aunque esos orígenes de datos enumerables se implementan de varias formas, todos revelan las mismas construcciones de lenguaje y sintaxis. Como las consultas se pueden formar en el lenguaje de programación mismo, no es necesario utilizar otro lenguaje de consultas que esté incrustado como literales de cadena que el compilador no pueda entender o comprobar. También integración de consultas en el lenguaje de programación permite a los programadores de Visual Studio ser más productivos proporcionando comprobación de sintaxis y tipo en tiempo de compilación y `IntelliSense`. Estas características reducen la necesidad de depuración y corrección de errores de consultas.  
  
 La transferencia de datos de las tablas de SQL a objetos de memoria a menudo es una tarea tediosa y propensa a errores. El proveedor de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] implementado por [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] y [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] convierte el origen de datos en recopilaciones de objetos basadas en <xref:System.Collections.IEnumerable>. El programador siempre ve los datos como una recopilación de <xref:System.Collections.IEnumerable> cuando se realiza la consulta y la actualización. Se proporciona compatibilidad completa con `IntelliSense` para escribir consultas en esas colecciones.  
  
 Existen tres tecnologías [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] de ADO.NET independientes: [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] y [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Proporciona consultas más ricas y optimizadas en el <xref:System.Data.DataSet> y [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] le permite consultar directamente los esquemas de base de datos de SQL Server, y [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] permite consultar un [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
 El siguiente diagrama proporciona una visión general de cómo se relacionan las tecnologías ADO.NET LINQ con lenguajes de programación de alto nivel y orígenes de datos habilitados para LINQ.  
  
 ![Información general ADO.NET LINQ to](../../../../docs/framework/data/adonet/media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 Para obtener información general sobre las características del lenguaje LINQ, vea [Introducción a LINQ](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e). Para obtener información sobre cómo usar LINQ en sus aplicaciones, consulte el [no en la compilación: Guía de programación de LINQ General](http://msdn.microsoft.com/library/609c7a6b-cbdd-429d-99f3-78d13d3bc049), que contiene información detallada sobre cómo utilizar las tecnologías LINQ.  
  
 En las siguientes secciones se proporciona más información acerca de [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] y [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> es un elemento fundamental del modelo de programación desconectada sobre el que se basa [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] y se usa ampliamente. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] permite a los programadores crear capacidades de consulta más complejas en <xref:System.Data.DataSet> utilizando el mismo mecanismo de formulación de consultas que está disponible para muchos otros orígenes de datos. Para más información, vea [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] es una herramienta útil para programadores que no requieren la asignación a un modelo conceptual. Si utiliza [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], puede usar el modelo de programación de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] directamente en un esquema de base de datos existente. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] permite a los programadores generar clases de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que representan datos. En lugar de la asignación a un modelo de datos conceptual, esas clases generadas se asignan directamente a tablas de bases de datos, vistas, procedimientos almacenados y funciones definidas por el usuario.  
  
 Con [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], los programadores pueden escribir código directamente en el esquema de almacenamiento usando el mismo patrón de programación de [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] que las recopilaciones en memoria y <xref:System.Data.DataSet>, además de otros orígenes de datos como XML. Para más información, vea [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 La mayor parte de las aplicaciones se escriben actualmente utilizando bases de datos relacionales. En algún punto, estas aplicaciones tendrán que interactuar con los datos representados en un formato relacional. Los esquemas de base de datos no siempre son ideales para crear aplicaciones y los modelos conceptuales de aplicación no son iguales que los modelos lógicos de bases de datos. [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] es un modelo de datos conceptual que se puede usar para crear un modelo de los datos de un dominio en particular para que las aplicaciones puedan interactuar con datos como objetos. Vea [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) para obtener más información.  
  
 A través de [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)], los datos relacionales se exponen como objetos en el entorno .NET. Esto hace de la capa de objetos un objetivo idóneo para la compatibilidad con [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], ya que permite a los programadores formular consultas en la base de datos con el lenguaje usado para compilar la lógica empresarial. Esta función se conoce como [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]. Para más información, vea [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vea también  
 [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)  
 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)  
 [LINQ (Language Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
