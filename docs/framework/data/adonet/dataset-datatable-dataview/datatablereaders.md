---
title: Objetos DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1ff7868b59c6fdc4e6c443be1b831accc84f36a6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203820"
---
# <a name="datatablereaders"></a>Objetos DataTableReader
El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.  
  
 Cuando se crea un **DataTableReader** a partir de una **DataTable**, el objeto **DataTableReader** resultante contiene un conjunto de resultados con los mismos datos que la **DataTable** desde la que se creó, excepto para las filas que se han marcado como borró. Las columnas aparecen en el mismo orden que en la **DataTable**original.  
  
 Un **DataTableReader** puede contener varios conjuntos de resultados si se creó mediante una <xref:System.Data.DataSet.CreateDataReader%2A>llamada a. Los resultados están en el mismo orden que los objetos **DataTable** de la colección del <xref:System.Data.DataSet.Tables%2A> objeto DataSet.  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de un objeto DataReader](creating-a-datareader.md)  
 Describe cómo crear un objeto **DataTableReader** .  
  
 [Navegación por objetos DataTables](navigating-datatables.md)  
 Describe el uso del método **Read** para desplazarse por el contenido de un **DataTableReader**.  
  
## <a name="see-also"></a>Vea también

- [Recuperar y modificar datos en ADO.NET](../retrieving-and-modifying-data.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
