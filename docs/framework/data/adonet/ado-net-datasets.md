---
title: DataSets
description: Obtenga información sobre el conjunto de datos, una representación de datos residente en memoria que proporciona un modelo de programación relacional coherente independientemente del origen de datos en ADO.NET.
ms.date: 03/30/2017
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
ms.openlocfilehash: d78918773c3cc88d8a925788d81cdafdc0a2db27
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153591"
---
# <a name="adonet-datasets"></a>Objetos DataSet de ADO.NET

El <xref:System.Data.DataSet> objeto es fundamental para admitir escenarios de datos distribuidos y desconectados con ADO.net. El **DataSet** es una representación residente en memoria de los datos que proporciona un modelo de programación relacional coherente independientemente del origen de datos. Se puede utilizar con muchos y distintos orígenes de datos, con datos XML o para administrar datos locales de la aplicación. El **DataSet** representa un conjunto completo de datos, incluidas las tablas relacionadas, las restricciones y las relaciones entre las tablas. En la ilustración siguiente se muestra el modelo de objetos **DataSet** .  
  
 ![Gráfico de ADO.NET](./media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Modelo de objetos DataSet  
  
 Los métodos y objetos de un **conjunto** de datos son coherentes con los del modelo de base de datos relacional.  
  
 El **DataSet** también puede conservar y volver a cargar su contenido como XML y su esquema como esquema del lenguaje de definición de esquemas XML (XSD). Para obtener más información, vea [Using XML in a DataSet](./dataset-datatable-dataview/using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).  
  
## <a name="the-datatablecollection"></a>DataTableCollection  

 Un **conjunto** de ADO.net contiene una colección de cero o más tablas representadas por <xref:System.Data.DataTable> objetos. <xref:System.Data.DataTableCollection>Contiene todos los objetos **DataTable** de un **DataSet**.  
  
 Un **DataTable** se define en el <xref:System.Data> espacio de nombres y representa una única tabla de datos residentes en memoria. Contiene una colección de columnas representadas por una <xref:System.Data.DataColumnCollection>, así como restricciones representadas por una <xref:System.Data.ConstraintCollection>, que juntas definen el esquema de la tabla. Un **objeto DataTable** también contiene una colección de filas representada por <xref:System.Data.DataRowCollection> , que contiene los datos de la tabla. Una <xref:System.Data.DataRow> conserva, junto con su estado actual, sus versiones actual y original para identificar los cambios en los valores almacenados en la fila.  
  
## <a name="the-dataview-class"></a>Clase DataView  

 Una <xref:System.Data.DataView> le permite crear diferentes vistas de los datos almacenados en una <xref:System.Data.DataTable>, una capacidad que suele utilizarse en aplicaciones de enlace a datos. Mediante <xref:System.Data.DataView> puede exponer los datos de una tabla con distintos criterios de ordenación y filtrar los datos por el estado de fila o basándose en una expresión de filtro. Para obtener más información, vea las [vistas](./dataset-datatable-dataview/dataviews.md)de datos.  
  
## <a name="the-datarelationcollection"></a>DataRelationCollection  

 Un **conjunto** de objetos contiene relaciones en su <xref:System.Data.DataRelationCollection> objeto. Una relación, representada por el <xref:System.Data.DataRelation> objeto, asocia las filas de un **DataTable** con las filas de otra **DataTable**. Las relaciones son análogas a las rutas de acceso de unión que podrían existir entre columnas de claves principales y externas en una base de datos relacional. Una **DataRelation** identifica las columnas coincidentes en dos tablas de un **DataSet**.  
  
 Las relaciones permiten la navegación de una tabla a otra en un **conjunto de DataSet**. Los elementos esenciales de una **DataRelation** son el nombre de la relación, el nombre de las tablas relacionadas y las columnas relacionadas de cada tabla. Es posible crear relaciones con más de una columna por tabla si se especifica una matriz de objetos <xref:System.Data.DataColumn> como columnas de claves. Cuando se agrega una relación a <xref:System.Data.DataRelationCollection> , opcionalmente se puede Agregar un **UniqueKeyConstraint** y una **ForeignKeyConstraint** para aplicar restricciones de integridad cuando se realizan cambios en los valores de columna relacionados.  
  
 Para obtener más información, vea [agregar objetos DataRelation](./dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  

 Puede rellenar un **conjunto** de documentos a partir de una secuencia o un documento XML. Puede utilizar la secuencia o el documento XML para proporcionar al **conjunto** de datos, información de esquema o ambas cosas. La información suministrada desde la secuencia o el documento XML puede combinarse con los datos existentes o la información de esquema que ya está presente en el **conjunto**de datos. Para obtener más información, vea [Using XML in a DataSet](./dataset-datatable-dataview/using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).  
  
## <a name="extendedproperties"></a>ExtendedProperties  

 Todos los **conjuntos**de propiedades, **DataTable**y **DataColumn** tienen una propiedad **ExtendedProperties** . **ExtendedProperties** es un **PropertyCollection** en el que puede colocar información personalizada, como la instrucción SELECT que se usó para generar el conjunto de resultados o la hora a la que se generaron los datos. La colección **ExtendedProperties** se conserva con la información de esquema del **conjunto**de datos.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  

 LINQ to DataSet proporciona funciones de consulta integradas en el lenguaje para los datos desconectados almacenados en un conjunto de datos. LINQ to DataSet usa la sintaxis estándar de LINQ y proporciona comprobación de sintaxis en tiempo de compilación, tipos estáticos y compatibilidad con IntelliSense cuando se usa el IDE de Visual Studio.  
  
 Para más información, vea [LINQ to DataSet](linq-to-dataset.md).  
  
## <a name="see-also"></a>Vea también

- [Información general de ADO.NET](ado-net-overview.md)
- [Objetos DataSet, DataTable y DataView](./dataset-datatable-dataview/index.md)
- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
