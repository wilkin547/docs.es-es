---
title: Objetos DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 911a45dad3d5d82ab5e5752b1c12f7d8a6ab1563
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202323"
---
# <a name="datatablereaders"></a>Objetos DataTableReader

El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.  
  
 Cuando se crea un **DataTableReader** a partir de un **DataTable**, el objeto **DataTableReader** resultante contiene un conjunto de resultados con los mismos datos que la **DataTable** desde la que se creó, excepto para las filas que se han marcado como eliminadas. Las columnas aparecen en el mismo orden que en la **DataTable**original.  
  
 Un **DataTableReader** puede contener varios conjuntos de resultados si se creó mediante una llamada a <xref:System.Data.DataSet.CreateDataReader%2A> . Los resultados están en el mismo orden que los objetos **DataTable** de la colección del objeto **DataSet** <xref:System.Data.DataSet.Tables%2A> .  
  
## <a name="in-this-section"></a>En esta sección  

 [Crear un objeto DataReader](creating-a-datareader.md)  
 Describe cómo crear un objeto **DataTableReader** .  
  
 [Navegar por objetos DataTable](navigating-datatables.md)  
 Describe el uso del método **Read** para desplazarse por el contenido de un **DataTableReader**.  
  
## <a name="see-also"></a>Consulte también

- [Recuperar y modificar datos en ADO.NET](../retrieving-and-modifying-data.md)
- [Información general de ADO.NET](../ado-net-overview.md)
