---
title: Procedimiento para crear un control DataGridView sin enlazar en formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: c488d0221080454a82e4c80f89964df0ee62f068
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591641"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a>Procedimiento para crear un control DataGridView sin enlazar en formularios Windows Forms
En el ejemplo de código siguiente se muestra cómo rellenar un control <xref:System.Windows.Forms.DataGridView> mediante programación sin enlazarlo a un origen de datos. Resulta de utilidad cuando tiene una pequeña cantidad de datos que quiere que se muestren en un formato de tabla.  
  
 Para obtener una explicación completa de este ejemplo de código, vea [Tutorial: Crear una independiente de Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Tutorial: Crear una independiente de Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Modos de presentación de datos en el control DataGridView de Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
