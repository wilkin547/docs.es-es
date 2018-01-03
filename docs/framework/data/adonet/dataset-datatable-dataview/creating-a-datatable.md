---
title: Crear un objeto DataTable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 68f8272aa0f525c04120f129057e6151e42ffee1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-datatable"></a>Crear un objeto DataTable
Un objeto <xref:System.Data.DataTable>, que representa una tabla de datos relacionales en la memoria, se puede crear y usar de manera independiente o lo pueden usar otros objetos de .NET Framework, normalmente como miembro de un objeto <xref:System.Data.DataSet>.  
  
 Puede crear un **DataTable** objeto mediante el uso adecuado **DataTable** constructor. Puede agregarlo a la **conjunto de datos** mediante el uso de la **agregar** método para agregarlo a la **DataTable** del objeto **tablas** colección.  
  
 También puede crear **DataTable** objetos dentro de un **conjunto de datos** mediante el uso de la **rellenar** o **FillSchema** métodos de la  **DataAdapter** objeto, o desde un predefinido o deducido esquema XML con el **ReadXml**, **ReadXmlSchema**, o **InferXmlSchema** métodos de la **conjunto de datos**. Tenga en cuenta que, después de haber agregado un **DataTable** como un miembro de la **tablas** colección de un **conjunto de datos**, no se puede agregar a la colección de tablas de ningún otro **Conjunto de datos**.  
  
 Cuando crea un **DataTable**, no tiene un esquema (es decir, una estructura). Para definir el esquema de la tabla, debe crear y agregar <xref:System.Data.DataColumn> objetos a la **columnas** colección de la tabla. También puede definir una columna de clave principal para la tabla y crear y agregar **restricción** objetos a la **restricciones** colección de la tabla. Después de haber definido el esquema para un **DataTable**, puede agregar filas de datos a la tabla agregando **DataRow** objetos a la **filas** colección de la tabla.  
  
 No se debe proporcionar un valor para el <xref:System.Data.DataTable.TableName%2A> propiedad cuando se crea un **DataTable**; puede especificar la propiedad en otro momento, o puede dejar vacío. Sin embargo, cuando se agrega una tabla sin un **TableName** valor a un **conjunto de datos**, la tabla recibirá un nombre predeterminado incremental de tabla*N*, comenzando por "Table" para Table0.  
  
> [!NOTE]
>  Se recomienda evitar la "tabla*N*" convención de nomenclatura al proporcionar un **TableName** valor, porque el nombre proporcionado puede entrar en conflicto con un nombre de tabla predeterminado existente en el **conjunto de datos** . Si el nombre proporcionado ya existe, se inicia una excepción.  
  
 En el ejemplo siguiente se crea una instancia de un **DataTable** objeto y le asigna el nombre "Customers".  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 En el ejemplo siguiente se crea una instancia de un **DataTable** agregándolo a la **tablas** colección de un **conjunto de datos**.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataTableCollection>  
 [Objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Rellenar un conjunto de datos desde un objeto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [Carga de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Carga de información del esquema de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
