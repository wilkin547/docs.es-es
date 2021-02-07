---
description: Más información acerca de cómo agregar restricciones existentes a un conjunto de información
title: Agregar restricciones existentes a un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: cad0dd1bd16747a5e76e10784d00c14cd9aa8c2a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729578"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>Agregar restricciones existentes a un conjunto de datos

El método **Fill** de **DataAdapter** rellena un <xref:System.Data.DataSet> solo con las columnas y filas de la tabla de un origen de datos; aunque el origen de datos suele establecer las restricciones, el método **Fill** no agrega esta información de esquema al **conjunto** de datos de forma predeterminada. Para rellenar un **conjunto** de datos con la información de restricciones PRIMARY KEY de un origen de datos, puede llamar al método **FillSchema** de **DataAdapter** o establecer la propiedad **MissingSchemaAction** de **DataAdapter** en **AddWithKey** antes de llamar a **Fill**. De esta forma se garantiza que las restricciones de clave principal del objeto **DataSet** reflejen las del origen de datos. La información de restricción de clave externa no se incluye y se debe crear explícitamente, como se muestra en [restricciones de DataTable](./dataset-datatable-dataview/datatable-constraints.md).  
  
Al agregar la información del esquema a un objeto **DataSet** antes de rellenarlo con datos, se garantiza que se incluyan las restricciones de clave principal con los objetos <xref:System.Data.DataTable> de **DataSet**. Como resultado, al realizar llamadas adicionales para rellenar el objeto **DataSet**, la información de la columna de clave principal se usa para hacer coincidir las nuevas filas del origen de datos con las filas actuales de cada instancia de **DataTable**, y los datos actuales de las tablas se sobrescriben con los del origen de datos. Sin la información del esquema, las filas nuevas del origen de datos se agregan al objeto **DataSet**, lo que genera filas duplicadas.  
  
> [!NOTE]
> Si una columna de un origen de datos se identifica como de incremento automático, el método **FillSchema** o el método **Fill** con el valor **MissingSchemaAction** de **AddWithKey**, crea un **DataColumn** con una propiedad **AutoIncrement** establecida en `true` . Pero en este caso tendrá que definir manualmente los valores **AutoIncrementStep** y **AutoIncrementSeed**. Para obtener más información acerca de las columnas de incremento automático, vea [crear columnas de incremento](./dataset-datatable-dataview/creating-autoincrement-columns.md)automático.  
  
Al usar **FillSchema** o establecer **MissingSchemaAction** en **AddWithKey**, se necesita procesamiento adicional en el origen de datos para determinar la información de la columna de clave principal. Este proceso adicional puede reducir el rendimiento. Si conoce en la fase de diseño la información de la clave principal, es aconsejable especificar de modo explícito la columna o columnas que la forman para mejorar el rendimiento. Para obtener información sobre cómo establecer explícitamente la información de clave principal de una tabla, vea [definir claves principales](./dataset-datatable-dataview/defining-primary-keys.md).
  
En el ejemplo de código siguiente se muestra cómo agregar información de esquema a un **conjunto** de datos mediante **FillSchema**:
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
En el ejemplo de código siguiente se muestra cómo agregar información de esquema a un **conjunto** de datos mediante la propiedad **MissingSchemaAction. AddWithKey** del método **Fill** :
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a>Control de varios conjuntos de resultados  

Si el **DataAdapter** encuentra varios conjuntos de resultados devueltos por **SelectCommand**, creará varias tablas en el **conjunto de DataSet**. Las tablas reciben de forma predeterminada un nombre secuencial de base cero **Table** *N*, comenzando por **Table** en lugar de "Table0". Si se pasa un nombre de tabla como argumento al método **FillSchema** , se asignará a las tablas un nombre incremental basado en cero de **TableName** *N*, comenzando por **TableName** en lugar de "representa tablename0".  
  
> [!NOTE]
> Si se llama al método **FillSchema** del objeto **OleDbDataAdapter** para un comando que devuelve varios conjuntos de resultados, solo se devuelve la información del esquema del primer conjunto de resultados. Al devolver información de esquema para varios conjuntos de resultados mediante **OleDbDataAdapter**, se recomienda especificar el **MissingSchemaAction** de **AddWithKey** y obtener la información del esquema al llamar al método **Fill** .  
  
## <a name="see-also"></a>Consulte también

- [Objetos DataAdapter y DataReader](dataadapters-and-datareaders.md)
- [Objetos DataSet, DataTable y DataView](./dataset-datatable-dataview/index.md)
- [Recuperar y modificar datos en ADO.NET](retrieving-and-modifying-data.md)
- [Información general de ADO.NET](ado-net-overview.md)
