---
title: Navegar por objetos DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 9b7ed4ef1dbe141d8f6a1b6c6b9af2fd89e6c7af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148313"
---
# <a name="navigating-datatables"></a>Navegar por objetos DataTable

El <xref:System.Data.DataTableReader> obtiene el contenido de uno o más objetos <xref:System.Data.DataTable> con formato de uno o más conjuntos de solo lectura y de solo avance.  
  
 Un <xref:System.Data.DataTableReader> puede contener varios conjuntos de resultados si se crea mediante el método <xref:System.Data.DataSet.CreateDataReader%2A>. Si hay más de un conjunto de resultados, el método <xref:System.Data.DataTableReader.NextResult%2A> desplaza el cursor hasta el siguiente conjunto de resultados. Este proceso es de solo avance. No es posible volver a un conjunto de resultados anterior.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, el `TestConstructor` método crea dos <xref:System.Data.DataTable> instancias de. Para mostrar este constructor para la <xref:System.Data.DataTableReader> clase, el ejemplo crea un nuevo **DataTableReader** basado en una matriz que contiene las dos **DataTables**y realiza una operación sencilla, imprimiendo el contenido de las primeras columnas en la ventana de la consola.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Objetos DataTableReader](datatablereaders.md)
- [Información general de ADO.NET](../ado-net-overview.md)
