---
title: Objetos DataSet de ADO.NET
ms.date: 03/30/2017
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
ms.openlocfilehash: 50e8e8f5e4b3ee2f5a41cb9dad11b5e701135d9e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190943"
---
# <a name="adonet-datasets"></a>Objetos DataSet de ADO.NET
El objeto <xref:System.Data.DataSet> es esencial para la compatibilidad con escenarios de datos distribuidos desconectados con [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. El **DataSet** es una representación residente en memoria de datos que proporciona un modelo de programación relacional coherente independientemente del origen de datos. Se puede utilizar con muchos y distintos orígenes de datos, con datos XML o para administrar datos locales de la aplicación. El **DataSet** representa un conjunto completo de datos, incluidas las tablas relacionadas, restricciones y relaciones entre las tablas. La siguiente ilustración muestra el **DataSet** modelo de objetos.  
  
 ![Gráfico de ADO.Net](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Modelo de objetos DataSet  
  
 Los métodos y objetos en un **DataSet** son coherentes con los del modelo de base de datos relacional.  
  
 El **DataSet** también puede mantener y recargar su contenido como XML y su esquema como esquema XML schema definition language (XSD). Para obtener más información, vea [Using XML in a DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).  
  
## <a name="the-datatablecollection"></a>DataTableCollection  
 Un [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **DataSet** contiene una colección de cero o más tablas representadas por <xref:System.Data.DataTable> objetos. El <xref:System.Data.DataTableCollection> contiene todos los **DataTable** objetos en un **DataSet**.  
  
 Un **DataTable** se define en el <xref:System.Data> espacio de nombres y representa una única tabla de datos residentes en memoria. Contiene una colección de columnas representadas por una <xref:System.Data.DataColumnCollection>, así como restricciones representadas por una <xref:System.Data.ConstraintCollection>, que juntas definen el esquema de la tabla. Un **DataTable** también contiene una colección de filas representadas por el <xref:System.Data.DataRowCollection>, que contiene los datos en la tabla. Una <xref:System.Data.DataRow> conserva, junto con su estado actual, sus versiones actual y original para identificar los cambios en los valores almacenados en la fila.  
  
## <a name="the-dataview-class"></a>Clase DataView  
 Una <xref:System.Data.DataView> le permite crear diferentes vistas de los datos almacenados en una <xref:System.Data.DataTable>, una capacidad que suele utilizarse en aplicaciones de enlace a datos. Mediante <xref:System.Data.DataView> puede exponer los datos de una tabla con distintos criterios de ordenación y filtrar los datos por el estado de fila o basándose en una expresión de filtro. Para obtener más información, consulte [DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>DataRelationCollection  
 Un **DataSet** contiene relaciones en su <xref:System.Data.DataRelationCollection> objeto. Una relación, representada por el <xref:System.Data.DataRelation> objeto, asocia las filas de una **DataTable** con las filas de otra **DataTable**. Las relaciones son análogas a las rutas de acceso de unión que podrían existir entre columnas de claves principales y externas en una base de datos relacional. Un **DataRelation** identifica las columnas coincidentes en dos tablas de un **DataSet**.  
  
 Las relaciones habilitan la navegación de una tabla a otra en un **DataSet**. Los elementos esenciales de un **DataRelation** son el nombre de la relación, el nombre de las tablas relacionadas y las columnas relacionadas de cada tabla. Es posible crear relaciones con más de una columna por tabla si se especifica una matriz de objetos <xref:System.Data.DataColumn> como columnas de claves. Al agregar una relación con el <xref:System.Data.DataRelationCollection>, opcionalmente, puede agregar un **UniqueKeyConstraint** y un **ForeignKeyConstraint** para exigir restricciones de integridad cuando se realizan cambios en la columna relacionada valores.  
  
 Para obtener más información, consulte [agregar objetos DataRelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  
 Puede rellenar un **DataSet** de un documento o secuencia XML. Puede usar el documento o secuencia XML para proporcionar a los **DataSet** datos, información de esquema o ambos. La información suministrada desde la secuencia o documento XML puede combinarse con datos existentes o información de esquema ya está presente en el **DataSet**. Para obtener más información, vea [Using XML in a DataSet](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 El **DataSet**, **DataTable**, y **DataColumn** todos tienen un **ExtendedProperties** propiedad. **Las propiedades extendidas** es un **PropertyCollection** donde puede colocar información personalizada, como la instrucción SELECT que se usó para generar el conjunto de resultados, o la hora cuando se generan los datos. El **ExtendedProperties** colección se mantiene con la información de esquema para el **DataSet**.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] proporciona capacidades language-integrated Query para datos desconectados almacenados en un conjunto de datos. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] usa estándar [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] sintaxis y proporciona comprobación de sintaxis en tiempo de compilación, tipos estáticos y compatibilidad con IntelliSense cuando se usa el IDE de Visual Studio.  
  
 Para más información, vea [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Objetos DataSet, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
