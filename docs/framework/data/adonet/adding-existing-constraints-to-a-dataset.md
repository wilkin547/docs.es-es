---
title: Agregar restricciones existentes a un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 05f95a9c4f250100ca97e3ab52e4073d027df1b8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932197"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>Agregar restricciones existentes a un conjunto de datos
El método **Fill** de **DataAdapter** rellena un <xref:System.Data.DataSet> solo con las columnas y filas de la tabla de un origen de datos; aunque el origen de datos suele establecer las restricciones, el método **Fill** no agrega esta información de esquema al  **Conjunto** de valores de forma predeterminada. Para rellenar un **conjunto** de datos con información de restricciones PRIMARY KEY de un origen de datos, puede llamar al método **FillSchema** de **DataAdapter**o establecer la propiedad **MissingSchemaAction** de **DataAdapter** . para que el método sea **AddWithKey** antes de llamar a **Fill**. Esto garantizará que las restricciones PRIMARY KEY del **conjunto** de datos reflejen las del origen de datos. La información de restricción de clave externa no se incluye y se debe crear explícitamente, como se muestra en [restricciones de DataTable](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Agregar información de esquema a un **conjunto** de datos antes de rellenarlo con datos garantiza que las restricciones PRIMARY <xref:System.Data.DataTable> Key se incluyen con los objetos del **conjunto**de datos. Como resultado, cuando se realizan llamadas adicionales para rellenar el **conjunto** de datos, la información de la columna de clave principal se utiliza para hacer coincidir las nuevas filas del origen de datos con las filas actuales de cada **DataTable**, y los datos actuales de las tablas se sobrescriben con los datos del origen de datos. Sin la información del esquema, las nuevas filas del origen de datos se anexan al **conjunto**de datos, lo que da lugar a filas duplicadas.  
  
> [!NOTE]
> Si una columna de un origen de datos se identifica como de incremento automático, el método **FillSchema** o el método **Fill** con el **MissingSchemaAction** de **AddWithKey**, crea un **DataColumn** con una propiedad AutoIncrement. establezca en `true`. Sin embargo, tendrá que establecer los valores de **AutoIncrementStep** y **AutoIncrementSeed** . Para obtener más información acerca de las columnas de incremento automático, vea [crear columnas de incremento](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md)automático.  
  
 El uso de **FillSchema** o el establecimiento de **MissingSchemaAction** en **AddWithKey** requiere un procesamiento adicional en el origen de datos para determinar la información de la columna de clave principal. Este proceso adicional puede reducir el rendimiento. Si conoce en la fase de diseño la información de la clave principal, es aconsejable especificar de modo explícito la columna o columnas que la forman para mejorar el rendimiento. Para obtener información sobre cómo establecer explícitamente la información de clave principal de una tabla, vea [definir claves principales](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 En el ejemplo de código siguiente se muestra cómo agregar información de esquema a un **conjunto** de datos mediante **FillSchema**.  
  
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
  
 En el ejemplo de código siguiente se muestra cómo agregar información de esquema a un **conjunto** de datos mediante la propiedad **MissingSchemaAction. AddWithKey** del método **Fill** .  
  
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
 Si el **DataAdapter** encuentra varios conjuntos de resultados devueltos por **SelectCommand**, creará varias tablas en el **conjunto de DataSet**. A las tablas se les asignará un nombre predeterminado incremental basado en cero de la **tabla** *N*, empezando por la **tabla** en lugar de "Table0". Si se pasa un nombre de tabla como argumento al método **FillSchema** , se asignará a las tablas un nombre incremental basado en cero de **TableName** *N*, comenzando por **TableName** en lugar de "representa tablename0".  
  
> [!NOTE]
> Si se llama al método **FillSchema** del objeto **OleDbDataAdapter** para un comando que devuelve varios conjuntos de resultados, solo se devuelve la información del esquema del primer conjunto de resultados. Al devolver información de esquema para varios conjuntos de resultados mediante **OleDbDataAdapter**, se recomienda especificar el **MissingSchemaAction** de **AddWithKey** y obtener la información del esquema al llamar al método **Fill** . forma.  
  
## <a name="see-also"></a>Vea también

- [Objetos DataAdapter y DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Objetos DataSet, DataTable y DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Recuperar y modificar datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
