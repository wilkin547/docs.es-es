---
title: "Agregar restricciones existentes a DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Agregar restricciones existentes a DataSet
El método **Fill** de **DataAdapter** llena un <xref:System.Data.DataSet> sólo con las columnas y filas de un origen de datos. Aunque las restricciones se suelen establecer en el origen de datos, el método **Fill** no agrega de forma predeterminada esta información del esquema al **DataSet**.  Para llenar un **DataSet** con la información de restricciones de clave principal existentes en el origen de datos, puede llamar al método **FillSchema** de **DataAdapter** o establecer la propiedad **MissingSchemaAction** de **DataAdapter** con el valor **AddWithKey** antes de llamar a **Fill**.  De esta forma se garantiza que las restricciones de clave principal del **DataSet** reflejan las del origen de datos.  La información de restricciones de clave externa no se incluye y se debe crear explícitamente, como se muestra en [Restricciones de DataTable](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Al agregar la información del esquema a un **DataSet** antes de llenarlo con datos, se garantiza que se incluyen las restricciones de clave principal con los objetos <xref:System.Data.DataTable> en el **DataSet**.  Como resultado, al realizar llamadas adicionales para llenar el **DataSet**, la información de la columna de clave principal se puede utilizar para hacer coincidir las nuevas filas del origen de datos con las filas actuales de cada una de las tablas **DataTable**, con lo que los datos actuales de las tablas se sobrescriben con los del origen de datos.  Sin la información del esquema, las filas nuevas del origen de datos se agregan al **DataSet**, con lo que se obtienen filas duplicadas.  
  
> [!NOTE]
>  Si una columna del origen de datos es de incremento automático, el método **FillSchema** o el método **Fill** con el valor **AddWithKey** en la propiedad **MissingSchemaAction** crean una **DataColumn** con el valor de la propiedad **AutoIncrement** establecido como `true`.  Sin embargo, en este caso debe definir manualmente los valores de **AutoIncrementStep** y **AutoIncrementSeed**.  Para obtener más información sobre las columnas de incremento automático, vea [Crear columnas AutoIncrement](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
 Al utilizar **FillSchema** o establecer el valor **AddWithKey** en **MissingSchemaAction**, se precisa un proceso adicional en el origen de datos para determinar la información de la columna de clave principal.  Este proceso adicional puede reducir el rendimiento.  Si conoce en la fase de diseño la información de la clave principal, es aconsejable especificar de modo explícito la columna o columnas que la forman para mejorar el rendimiento.  Para obtener más información sobre la especificación de modo explícito de información de la clave principal de una tabla, vea [Definir claves principales](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 En el ejemplo de código siguiente se muestra cómo agregar la información del esquema a un **DataSet** mediante **FillSchema**.  
  
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
  
 En el ejemplo de código siguiente se muestra la forma de agregar la información del esquema a un **DataSet** mediante la propiedad **MissingSchemaAction.AddWithKey** del método **Fill**.  
  
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
  
## Controlar varios conjuntos de resultados  
 Cuando **DataAdapter** encuentra varios conjuntos de resultados devueltos por **SelectCommand**, crea varias tablas en el **DataSet**.  Las tablas reciben de forma predeterminada el nombre secuencial que comienza en cero **Table** *N*, comenzando por **Table** en lugar de "Table0".  Si se pasa un nombre de tabla como argumento al método **FillSchema**, las tablas reciben el nombre secuencial que comienza por cero **TableName** *N*, comenzando por **TableName** en lugar de "TableName0".  
  
> [!NOTE]
>  Si se llama al método **FillSchema** del objeto **OleDbDataAdapter** para un comando que devuelve múltiples conjuntos de resultados, sólo se devuelve la información del esquema del primer conjunto de resultados.  Al devolver la información del esquema de múltiples conjuntos de resultados mediante **OleDbDataAdapter**, es aconsejable asignar a la propiedad **MissingSchemaAction** el valor **AddWithKey** y obtener la información del esquema al llamar al método **Fill**.  
  
## Vea también  
 [DataAdapters y DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [DataSets, DataTables y DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Recuperación y modificación de datos en ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)