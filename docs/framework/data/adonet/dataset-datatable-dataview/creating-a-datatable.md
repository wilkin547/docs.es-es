---
title: Crear un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: b56d2f8cd46f3184f1001c8bd6a70dbfc4968968
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937029"
---
# <a name="creating-a-datatable"></a>Crear un objeto DataTable
Un objeto <xref:System.Data.DataTable>, que representa una tabla de datos relacionales en la memoria, se puede crear y usar de manera independiente o lo pueden usar otros objetos de .NET Framework, normalmente como miembro de un objeto <xref:System.Data.DataSet>.  
  
 Puede crear un objeto **DataTable** mediante el constructor de **DataTable** adecuado. Puede agregarlo al **conjunto** de objetos mediante el método **Add** para agregarlo a la colección de **tablas** del objeto **DataTable** .  
  
 También puede crear objetos **DataTable** dentro de un **conjunto de DataSet** mediante los métodos **Fill** o **FillSchema** del objeto **DataAdapter** o desde un esquema XML predefinido o deducido mediante el **ReadXml**, **ReadXmlSchema** o métodos **InferXmlSchema** del conjunto de **DataSet**. Tenga en cuenta que después de haber agregado un **DataTable** como miembro de la colección tables de un **DataSet**, no puede agregarlo a la colección de tablas de ningún otro **conjunto**de tipos.  
  
 La primera vez que se crea un **objeto DataTable**, no tiene un esquema (es decir, una estructura). Para definir el esquema de la tabla, debe crear y agregar <xref:System.Data.DataColumn> objetos a la colección **Columns** de la tabla. También puede definir una columna de clave principal para la tabla y crear y agregar objetos de **restricción** a la colección **Constraints** de la tabla. Después de haber definido el esquema para un **DataTable**, puede Agregar filas de datos a la tabla agregando objetos **DataRow** a la colección **Rows** de la tabla.  
  
 No es necesario proporcionar un valor para la <xref:System.Data.DataTable.TableName%2A> propiedad cuando se crea un **objeto DataTable**; puede especificar la propiedad en otro momento o dejarla vacía. Sin embargo, cuando se agrega una tabla sin un valor **TableName** a un **conjunto**de valores, se asigna a la tabla un nombre predeterminado incremental de la tabla*N*, que empieza por "Table" para Table0.  
  
> [!NOTE]
> Se recomienda evitar la Convención de nomenclatura "Table*N*" al proporcionar un valor **TableName** , ya que el nombre proporcionado puede entrar en conflicto con un nombre de tabla predeterminado existente en el **conjunto de DataSet**. Si el nombre proporcionado ya existe, se inicia una excepción.  
  
 En el ejemplo siguiente se crea una instancia de un objeto **DataTable** y se le asigna el nombre "Customers".  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 En el ejemplo siguiente se crea una instancia de un **objeto DataTable** agregándolo a la colección tables de un **DataSet**.  
  
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

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [Objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Rellenar un conjunto de datos desde un objeto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [Carga de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [Carga de información del esquema de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
