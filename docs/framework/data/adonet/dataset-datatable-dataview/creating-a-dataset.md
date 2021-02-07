---
description: Más información acerca de cómo crear un conjunto de información
title: Crear un objeto DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: 7a52c6e73b5ab3ba4bf384d6bab3640b85929fcc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739656"
---
# <a name="creating-a-dataset"></a>Crear un objeto DataSet

Puede crear una instancia de <xref:System.Data.DataSet> llamando al constructor <xref:System.Data.DataSet>. Si lo desea, especifique un nombre de argumento. Si no especifica ningún nombre para el <xref:System.Data.DataSet>, se establecerá el nombre "NewDataSet".  
  
 También es posible crear un nuevo <xref:System.Data.DataSet> basado en un <xref:System.Data.DataSet>existente. El nuevo <xref:System.Data.DataSet> puede ser una copia exacta del <xref:System.Data.DataSet> existente; un clon del <xref:System.Data.DataSet> que copia la estructura relacional o el esquema, pero que no contiene ningún dato del <xref:System.Data.DataSet> existente; o un subconjunto del <xref:System.Data.DataSet>, que contiene solamente las filas modificadas del <xref:System.Data.DataSet> existente mediante el método <xref:System.Data.DataSet.GetChanges%2A>. Para obtener más información, vea [copiar el contenido del conjunto](copying-dataset-contents.md)de datos.  
  
 En el siguiente ejemplo de código se muestra cómo construir una instancia de un <xref:System.Data.DataSet>.  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a>Vea también

- [Rellenar un conjunto de datos desde un objeto DataAdapter](../populating-a-dataset-from-a-dataadapter.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
