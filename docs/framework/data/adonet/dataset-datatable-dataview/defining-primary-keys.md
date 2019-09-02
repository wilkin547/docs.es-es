---
title: Definir claves principales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: dbfd8a8b207c0da9403ac1f8ab36557c4abe383b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204912"
---
# <a name="defining-primary-keys"></a><span data-ttu-id="789d7-102">Definir claves principales</span><span class="sxs-lookup"><span data-stu-id="789d7-102">Defining Primary Keys</span></span>
<span data-ttu-id="789d7-103">Generalmente, una tabla de base de datos tiene una columna o grupo de columnas que identifican de manera exclusiva cada fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="789d7-103">A database table commonly has a column or group of columns that uniquely identifies each row in the table.</span></span> <span data-ttu-id="789d7-104">Esta columna o grupo de columnas de identificación se denomina clave principal.</span><span class="sxs-lookup"><span data-stu-id="789d7-104">This identifying column or group of columns is called the primary key.</span></span>  
  
 <span data-ttu-id="789d7-105">Al identificar un único <xref:System.Data.DataColumn> <xref:System.Data.DataTable> <xref:System.Data.DataColumn.Unique%2A> <xref:System.Data.DataColumn.AllowDBNull%2A>como para, la tabla establece automáticamente la propiedad de la columna en false y la propiedad en true. <xref:System.Data.DataTable.PrimaryKey%2A></span><span class="sxs-lookup"><span data-stu-id="789d7-105">When you identify a single <xref:System.Data.DataColumn> as the <xref:System.Data.DataTable.PrimaryKey%2A> for a <xref:System.Data.DataTable>, the table automatically sets the <xref:System.Data.DataColumn.AllowDBNull%2A> property of the column to **false** and the <xref:System.Data.DataColumn.Unique%2A> property to **true**.</span></span> <span data-ttu-id="789d7-106">En el caso de las claves principales de varias columnas, solo la propiedad **AllowDBNull** se establece automáticamente en **false**.</span><span class="sxs-lookup"><span data-stu-id="789d7-106">For multiple-column primary keys, only the **AllowDBNull** property is automatically set to **false**.</span></span>  
  
 <span data-ttu-id="789d7-107">La propiedad **PrimaryKey** de una <xref:System.Data.DataTable> recibe como valor una matriz de uno o más objetos **DataColumn** , como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="789d7-107">The **PrimaryKey** property of a <xref:System.Data.DataTable> receives as its value an array of one or more **DataColumn** objects, as shown in the following examples.</span></span> <span data-ttu-id="789d7-108">En el primer ejemplo se define una sola columna como clave principal.</span><span class="sxs-lookup"><span data-stu-id="789d7-108">The first example defines a single column as the primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 <span data-ttu-id="789d7-109">En el siguiente ejemplo se definen dos columnas como clave principal.</span><span class="sxs-lookup"><span data-stu-id="789d7-109">The following example defines two columns as a primary key.</span></span>  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a><span data-ttu-id="789d7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="789d7-110">See also</span></span>

- <xref:System.Data.DataTable>
- [<span data-ttu-id="789d7-111">Definición del esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="789d7-111">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="789d7-112">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="789d7-112">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="789d7-113">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="789d7-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
