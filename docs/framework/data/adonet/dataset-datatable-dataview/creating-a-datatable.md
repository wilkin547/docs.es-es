---
title: Crear un objeto DataTable
description: Aprenda a crear un objeto DataTable en ADO.NET, que representa una tabla de datos relacionales en memoria, para usar de forma independiente u otros objetos .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 335137eeef02e590539c6d83e46cb39901a1e03f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286926"
---
# <a name="creating-a-datatable"></a>Crear un objeto DataTable
Un objeto <xref:System.Data.DataTable>, que representa una tabla de datos relacionales en la memoria, se puede crear y usar de manera independiente o lo pueden usar otros objetos de .NET Framework, normalmente como miembro de un objeto <xref:System.Data.DataSet>.  
  
 Puede crear un objeto **DataTable** mediante el constructor de **DataTable** adecuado. Puede agregarlo al **conjunto** de objetos mediante el método **Add** para agregarlo a la colección de **tablas** del objeto **DataTable** .  
  
 También puede crear objetos **DataTable** dentro de un **conjunto de DataSet** mediante los métodos **Fill** o **FillSchema** del objeto **DataAdapter** , o desde un esquema XML predefinido o deducido mediante los métodos **ReadXml**, **ReadXmlSchema**o **InferXmlSchema** del **conjunto**de objetos. Tenga en cuenta que después de haber agregado un **DataTable** como miembro de la colección **tables** de un **DataSet**, no puede agregarlo a la colección de tablas de ningún otro **conjunto**de tipos.  
  
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
  
 En el ejemplo siguiente se crea una instancia de un **objeto DataTable** agregándolo a la colección **tables** de un **DataSet**.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [Objetos DataTable](datatables.md)
- [Rellenar un conjunto de datos desde un objeto DataAdapter](../populating-a-dataset-from-a-dataadapter.md)
- [Cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Cargar información del esquema de un conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md)
- [Información general de ADO.NET](../ado-net-overview.md)
