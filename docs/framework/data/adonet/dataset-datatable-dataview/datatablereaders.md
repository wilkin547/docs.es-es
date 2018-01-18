---
title: Objetos DataTableReader
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b5160f5a2c68cab798dde154275c062e2bf31739
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="datatablereaders"></a>Objetos DataTableReader
El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.  
  
 Cuando se crea un **DataTableReader** desde una **DataTable**, resultante **DataTableReader** objeto contiene un conjunto de resultados con los mismos datos que el  **DataTable** desde que se creó, excepto las filas que se han marcado como eliminada. Las columnas aparecen en el mismo orden que en la versión original **DataTable**.  
  
 A **DataTableReader** puede contener varios conjuntos de resultados si se ha creado mediante una llamada a <xref:System.Data.DataSet.CreateDataReader%2A>. Los resultados están en el mismo orden que el **DataTables** en el **conjunto de datos** del objeto <xref:System.Data.DataSet.Tables%2A> colección.  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de un objeto DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Describe cómo crear un **DataTableReader** objeto.  
  
 [Navegación por objetos DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Describe el uso de la **lectura** método para desplazarse por el contenido de un **DataTableReader**.  
  
## <a name="see-also"></a>Vea también  
 [Recuperar y modificar datos en ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
