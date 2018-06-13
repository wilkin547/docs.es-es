---
title: Agregar restricciones existentes a un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: c3c28392a9e4bee0e2f9e0dcf553e13b67c378dd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758362"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>Agregar restricciones existentes a un conjunto de datos
El **rellenar** método de la **DataAdapter** rellena un <xref:System.Data.DataSet> sólo con las columnas y filas de un origen de datos; aunque las restricciones se suelen establecer en el origen de datos, el **derelleno** método no agrega esta información de esquema para el **conjunto de datos** de forma predeterminada. Para rellenar un **conjunto de datos** con la información de restricción de clave principal existente de un origen de datos, puede llamar a la **FillSchema** método de la **DataAdapter**, o establecer la **MissingSchemaAction** propiedad de la **DataAdapter** a **AddWithKey** antes de llamar a **rellenar**. Así asegurará de que la clave principal restricciones en la **conjunto de datos** las del origen de datos reflejan. Información de restricción de clave externa no están incluidas y deben crearse de forma explícita, como se muestra en [restricciones de DataTable](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Agregar información del esquema a un **conjunto de datos** antes de llenarlo con datos garantiza que las restricciones primary key se incluyen con el <xref:System.Data.DataTable> objetos en el **conjunto de datos**. Como resultado, cuando adicionales llamadas para rellenar el **conjunto de datos** se realizan, la principal información de columna de clave se usa para hacer coincidir filas nuevas del origen de datos con las filas actuales en cada uno **DataTable**y los datos actuales en las tablas se sobrescriben con datos procedentes del origen de datos. Sin la información de esquema, las nuevas filas del origen de datos se anexan a la **conjunto de datos**, da lugar a las filas duplicadas.  
  
> [!NOTE]
>  Si una columna de un origen de datos se identifica como incremento automático, el **FillSchema** método, o la **rellenar** método con un **MissingSchemaAction** de  **AddWithKey**, crea un **DataColumn** con una **AutoIncrement** propiedad establecida en `true`. Sin embargo, debe establecer el **AutoIncrementStep** y **AutoIncrementSeed** valores usted mismo. Para obtener más información acerca de las columnas de incremento automático, consulte [crear columnas de incremento automático](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
 Usar **FillSchema** o la configuración de la **MissingSchemaAction** a **AddWithKey** requiere un procesamiento adicional en el origen de datos para determinar la información de columna de clave principal. Este proceso adicional puede reducir el rendimiento. Si conoce en la fase de diseño la información de la clave principal, es aconsejable especificar de modo explícito la columna o columnas que la forman para mejorar el rendimiento. Para obtener información acerca de cómo establecer explícitamente la información de clave principal para una tabla, vea [definir claves principales](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 En el ejemplo de código siguiente se muestra cómo agregar información de esquema a un **conjunto de datos** con **FillSchema**.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 En el ejemplo de código siguiente se muestra cómo agregar información de esquema a un **conjunto de datos** mediante la **MissingSchemaAction.AddWithKey** propiedad de la **rellenar** método.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a>Controlar varios conjuntos de resultados  
 Si el **DataAdapter** encuentra varios conjuntos de resultados devueltos por la **SelectCommand**, creará varias tablas en el **conjunto de datos**. Las tablas se proporcionará un nombre predeterminado incremental basado en cero de **tabla** *N*, comenzando por **tabla** en lugar de "Table0". Si se pasa un nombre de tabla como argumento a la **FillSchema** método, las tablas se proporcionará un nombre basado en cero de **TableName** *N*, comenzando por **TableName** en lugar de "TableName0".  
  
> [!NOTE]
>  Si el **FillSchema** método de la **OleDbDataAdapter** objeto se llama para un comando que devuelve múltiples conjuntos de resultados, se devuelve la información de esquema del primer conjunto de resultados. Al devolver la información de esquema de resultados múltiples conjuntos de uso de la **OleDbDataAdapter**, se recomienda que especifique una **MissingSchemaAction** de **AddWithKey** y obtener la información del esquema al llamar a la **rellenar** método.  
  
## <a name="see-also"></a>Vea también  
 [Objetos DataAdapter y DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Objetos DataSet, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
