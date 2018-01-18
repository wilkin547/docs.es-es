---
title: Navegar por objetos DataTable
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
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2233beeab5bc613966375f9a8ccf18c333e9f4c6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="navigating-datatables"></a>Navegar por objetos DataTable
El <xref:System.Data.DataTableReader> obtiene el contenido de uno o más objetos <xref:System.Data.DataTable> con formato de uno o más conjuntos de solo lectura y de solo avance.  
  
 Un <xref:System.Data.DataTableReader> puede contener varios conjuntos de resultados si se crea mediante el método <xref:System.Data.DataSet.CreateDataReader%2A>. Si hay más de un conjunto de resultados, el método <xref:System.Data.DataTableReader.NextResult%2A> desplaza el cursor hasta el siguiente conjunto de resultados. Este proceso es de solo avance. No es posible volver a un conjunto de resultados anterior.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la `TestConstructor` método crea dos <xref:System.Data.DataTable> instancias. Para mostrar este constructor para la <xref:System.Data.DataTableReader> (clase), el ejemplo se crea un nuevo **DataTableReader** basado en una matriz que contiene las dos **DataTables**y realiza una operación sencilla, Imprime el contenido de las primeras columnas en la ventana de consola.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Objetos DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
