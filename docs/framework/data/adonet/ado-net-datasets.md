---
title: "Objetos DataSet de ADO.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Objetos DataSet de ADO.NET
El <xref:System.Data.DataSet> objeto desconectado, es esencial para admitir datos escenarios distribuidos con [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. El **DataSet** es una representación residente en memoria de datos que proporciona un modelo de programación relacional coherente independientemente del origen de datos. Se puede utilizar con muchos y distintos orígenes de datos, con datos XML o para administrar datos locales de la aplicación. El **DataSet** representa un conjunto completo de datos, incluidas tablas relacionadas, restricciones y relaciones entre las tablas. La siguiente ilustración muestra la **DataSet** modelo de objetos.  
  
 ![Gráfico de ADO.Net](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Modelo de objetos DataSet  
  
 Los métodos y objetos de un **DataSet** son coherentes con los del modelo de base de datos relacional.  
  
 El **DataSet** también puede mantener y recargar su contenido como XML y su esquema como esquema de lenguaje (XSD) de definición de esquemas XML. Para obtener más información, consulte [mediante XML en un conjunto de datos](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="the-datatablecollection"></a>DataTableCollection  
 Un [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **DataSet** contiene una colección de cero o más tablas representadas por <xref:System.Data.DataTable> objetos. El <xref:System.Data.DataTableCollection> contiene todos los **DataTable** objetos en un **conjunto de datos**.  
  
 Un **DataTable** se define en el <xref:System.Data> espacio de nombres y representa una única tabla de datos residentes en memoria. Contiene una colección de columnas representadas por una <xref:System.Data.DataColumnCollection>así como restricciones representadas por una <xref:System.Data.ConstraintCollection>, que juntas definen el esquema de la tabla. Un **DataTable** también contiene una colección de filas representadas por la <xref:System.Data.DataRowCollection>, que contiene los datos de la tabla. Junto con su estado actual, un <xref:System.Data.DataRow> conserva sus versiones actuales y originales para identificar los cambios en los valores almacenados en la fila.  
  
## <a name="the-dataview-class"></a>Clase DataView  
 Un <xref:System.Data.DataView> le permite crear diferentes vistas de los datos almacenados en una <xref:System.Data.DataTable>, una capacidad que suele utilizarse en aplicaciones de enlace de datos. Con un <xref:System.Data.DataView>, puede exponer los datos en una tabla con distintos criterios de ordenación y puede filtrar los datos por estado de fila o basándose en una expresión de filtro. Para obtener más información, consulte [DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>DataRelationCollection  
 Un **DataSet** contiene relaciones en su <xref:System.Data.DataRelationCollection> objeto. Una relación, representada por la <xref:System.Data.DataRelation> objeto, asocia las filas de una **DataTable** con filas de otra **DataTable**. Las relaciones son análogas a las rutas de acceso de unión que podrían existir entre columnas de claves principales y externas en una base de datos relacional. Un **DataRelation** identifica las columnas coincidentes en dos tablas de un **conjunto de datos**.  
  
 Las relaciones habilitan la navegación entre tablas en un **conjunto de datos**. Los elementos esenciales de un **DataRelation** son el nombre de la relación, el nombre de las tablas relacionadas y las columnas relacionadas de cada tabla. Crear relaciones con más de una columna por tabla especificando una matriz de <xref:System.Data.DataColumn> objetos como columnas de clave. Al agregar una relación con la <xref:System.Data.DataRelationCollection>, puede agregar opcionalmente una **UniqueKeyConstraint** y un **ForeignKeyConstraint** para exigir restricciones de integridad cuando se realizan cambios en valores de columna relacionados.  
  
 Para obtener más información, consulte [Agregar DataRelations](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  
 Puede rellenar un **conjunto de datos** de un documento o secuencia XML. Puede utilizar la secuencia o documento XML para suministrar la **conjunto de datos** datos, información de esquema o ambos. La información suministrada desde la secuencia o documento XML puede combinarse con datos existentes o información de esquema ya presente en el **conjunto de datos**. Para obtener más información, consulte [mediante XML en un conjunto de datos](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 El **DataSet**, **DataTable**, y **DataColumn** todos tienen un **ExtendedProperties** propiedad. **ExtendedProperties** es una **PropertyCollection** donde puede colocar información personalizada, como la instrucción SELECT que se utilizó para generar el conjunto de resultados o la hora cuando se generaron los datos. El **ExtendedProperties** colección se conserva con la información de esquema para el **conjunto de datos**.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] proporciona capacidades LINQ (Language Integrated Query) para datos desconectados almacenados en DataSet. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]usa estándar [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] sintaxis y proporciona comprobación de sintaxis en tiempo de compilación, tipos estáticos y compatibilidad con IntelliSense cuando se usa el [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] IDE.  
  
 Para obtener más información, consulte [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [DataSet, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Centro de desarrolladores de conjunto de datos y proveedores administrados de ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)