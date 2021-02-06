---
description: 'Más información acerca de: objetos DataTableReader'
title: Objetos DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: b3e85ae05c07af18fe6219602b5b40f50a9fbc8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652606"
---
# <a name="datatablereaders"></a>Objetos DataTableReader

El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.  
  
 Cuando se crea un **DataTableReader** a partir de un **DataTable**, el objeto **DataTableReader** resultante contiene un conjunto de resultados con los mismos datos que la **DataTable** desde la que se creó, excepto para las filas que se han marcado como eliminadas. Las columnas aparecen en el mismo orden que en la **DataTable** original.  
  
 Un **DataTableReader** puede contener varios conjuntos de resultados si se creó mediante una llamada a <xref:System.Data.DataSet.CreateDataReader%2A> . Los resultados están en el mismo orden que los objetos **DataTable** de la colección del objeto **DataSet** <xref:System.Data.DataSet.Tables%2A> .  
  
## <a name="in-this-section"></a>En esta sección  

 [Crear un objeto DataReader](creating-a-datareader.md)  
 Describe cómo crear un objeto **DataTableReader** .  
  
 [Navegar por objetos DataTable](navigating-datatables.md)  
 Describe el uso del método **Read** para desplazarse por el contenido de un **DataTableReader**.  
  
## <a name="see-also"></a>Vea también

- [Recuperar y modificar datos en ADO.NET](../retrieving-and-modifying-data.md)
- [Información general de ADO.NET](../ado-net-overview.md)
