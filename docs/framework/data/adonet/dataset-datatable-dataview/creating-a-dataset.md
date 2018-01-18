---
title: Crear un objeto DataSet
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
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 565d407dda3a3ac403dc92ad294af8fd1b5dfd70
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="creating-a-dataset"></a>Crear un objeto DataSet
Puede crear una instancia de <xref:System.Data.DataSet> llamando al constructor <xref:System.Data.DataSet>. Si lo desea, especifique un nombre de argumento. Si no especifica ningún nombre para el <xref:System.Data.DataSet>, se establecerá el nombre "NewDataSet".  
  
 También es posible crear un nuevo <xref:System.Data.DataSet> basado en un <xref:System.Data.DataSet>existente. El nuevo <xref:System.Data.DataSet> puede ser una copia exacta del <xref:System.Data.DataSet> existente; un clon del <xref:System.Data.DataSet> que copia la estructura relacional o el esquema, pero que no contiene ningún dato del <xref:System.Data.DataSet> existente; o un subconjunto del <xref:System.Data.DataSet>, que contiene solamente las filas modificadas del <xref:System.Data.DataSet> existente mediante el método <xref:System.Data.DataSet.GetChanges%2A>. Para obtener más información, consulte [copiar contenido de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).  
  
 En el siguiente ejemplo de código se muestra cómo construir una instancia de un <xref:System.Data.DataSet>.  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a>Vea también  
 [Rellenar un conjunto de datos desde un objeto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
