---
title: LINQ y ADO.NET
titleSuffix: ''
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: e24473f68fe5ccd993c5d205660ea8f397b6f797
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980098"
---
# <a name="linq-and-adonet"></a>LINQ y ADO.NET
En la actualidad, muchos desarrolladores empresariales deben usar dos (o más) lenguajes de programación: un lenguaje de alto nivel para los niveles de presentación y lógica C# empresarial (como Visual o Visual Basic) y un lenguaje de consulta para interactuar con la base de datos (como TRANSACT-SQL). Esto requiere que el programador tenga conocimientos de varios idiomas para ser efectivo y también causa discrepancias de idiomas en el entorno de desarrollo. Por ejemplo, una aplicación que utiliza API de acceso a datos para ejecutar una consulta en una base de datos especifica la consulta como un literal de cadena usando comillas. Esta cadena de consulta es ilegible y no se comprueba si contiene errores, tales como una sintaxis no válida o si existen las columnas o las filas a las que hace referencia. No hay ninguna comprobación de tipo de los parámetros de consulta y tampoco hay compatibilidad con `IntelliSense`.  
  
 Language-Integrated Query (LINQ) permite a los desarrolladores crear consultas basadas en conjuntos en su código de aplicación, sin tener que usar un lenguaje de consulta independiente. Puede escribir consultas LINQ en varios orígenes de datos enumerables (es decir, un origen de datos que implementa la interfaz <xref:System.Collections.IEnumerable>), como estructuras de datos en memoria, documentos XML, bases de datos SQL y objetos <xref:System.Data.DataSet>. Aunque esos orígenes de datos enumerables se implementan de varias formas, todos revelan las mismas construcciones de lenguaje y sintaxis. Como las consultas se pueden formar en el lenguaje de programación mismo, no es necesario utilizar otro lenguaje de consultas que esté incrustado como literales de cadena que el compilador no pueda entender o comprobar. La integración de consultas en el lenguaje de programación también permite que los programadores de Visual Studio sean más productivos al proporcionar comprobación de sintaxis y tipos en tiempo de compilación, y `IntelliSense`. Estas características reducen la necesidad de depuración y corrección de errores de consultas.  
  
 La transferencia de datos de las tablas de SQL a objetos de memoria a menudo es una tarea tediosa y propensa a errores. El proveedor LINQ implementado por LINQ to DataSet y [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] convierte los datos de origen en colecciones de objetos basadas en <xref:System.Collections.IEnumerable>. El programador siempre ve los datos como una colección de <xref:System.Collections.IEnumerable> cuando se realiza la consulta y la actualización. Se proporciona compatibilidad completa con `IntelliSense` para escribir consultas en esas colecciones.  
  
 Hay tres tecnologías de ADO.NET Language Integrated Query (LINQ) independientes: LINQ to DataSet, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]y LINQ to Entities. LINQ to DataSet proporciona consultas más enriquecidas y optimizadas en el <xref:System.Data.DataSet> y [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] le permite consultar directamente esquemas de base de datos de SQL Server y LINQ to Entities le permite consultar una Entity Data Model.  
  
 El siguiente diagrama proporciona una visión general de cómo se relacionan las tecnologías ADO.NET LINQ con lenguajes de programación de alto nivel y orígenes de datos habilitados para LINQ.  
  
 ![Información general de LINQ to ADO.NET](./media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 Para obtener más información sobre LINQ, vea [Language Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).
  
 En las secciones siguientes se proporciona más información acerca de LINQ to DataSet, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]y LINQ to Entities.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 El <xref:System.Data.DataSet> es un elemento clave del modelo de programación desconectado en el que se basa ADO.NET y se usa ampliamente. LINQ to DataSet permite a los desarrolladores crear funciones de consulta más enriquecidas en <xref:System.Data.DataSet> mediante el mismo mecanismo de formulación de consultas que está disponible para muchos otros orígenes de datos. Para más información, vea [LINQ to DataSet](linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] es una herramienta útil para programadores que no requieren la asignación a un modelo conceptual. Con [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], puede utilizar el modelo de programación LINQ directamente sobre el esquema de la base de datos existente. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] permite a los desarrolladores generar .NET Framework clases que representan datos. En lugar de la asignación a un modelo de datos conceptual, esas clases generadas se asignan directamente a tablas de bases de datos, vistas, procedimientos almacenados y funciones definidas por el usuario.  
  
 Con [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], los desarrolladores pueden escribir código directamente en el esquema de almacenamiento mediante el mismo modelo de programación de LINQ que las colecciones en memoria y el <xref:System.Data.DataSet>, además de otros orígenes de datos como XML. Para más información, vea [LINQ to SQL](./sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 La mayor parte de las aplicaciones se escriben actualmente utilizando bases de datos relacionales. En algún punto, estas aplicaciones tendrán que interactuar con los datos representados en un formato relacional. Los esquemas de base de datos no siempre son ideales para crear aplicaciones y los modelos conceptuales de aplicación no son iguales que los modelos lógicos de bases de datos. La Entity Data Model es un modelo de datos conceptual que se puede usar para modelar los datos de un dominio determinado para que las aplicaciones puedan interactuar con los datos como objetos. Consulte [ADO.NET Entity Framework](./ef/index.md) para obtener más información.  
  
 A través del modelo Entity Data Model, los datos relacionales se exponen como objetos en el entorno .NET. Esto hace de la capa de objetos un objetivo idóneo para la compatibilidad con LINQ, ya que permite a los programadores formular consultas en la base de datos con el lenguaje usado para compilar la lógica empresarial. Esta funcionalidad se conoce como LINQ to Entities. Para más información, vea [LINQ to Entities](./ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Vea también

- [LINQ to DataSet](linq-to-dataset.md)
- [LINQ to SQL](./sql/linq/index.md)
- [LINQ to Entities](./ef/language-reference/linq-to-entities.md)
- [Language-Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md)
- [Información general sobre ADO.NET](ado-net-overview.md)
