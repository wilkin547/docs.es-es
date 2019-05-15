---
title: Procedimiento para manipular bandas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], manipulating bands
- bands [Windows Forms], manipulating in Windows Forms
- DataGridView control [Windows Forms], manipulating bands
ms.assetid: 1ea3470e-480f-4edc-bcbd-51373eca3856
ms.openlocfilehash: 5e62f5d31b9d24469455ab31f9771ebc81f74967
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592347"
---
# <a name="how-to-manipulate-bands-in-the-windows-forms-datagridview-control"></a>Procedimiento para manipular bandas en el control DataGridView de formularios Windows Forms
En el ejemplo de código siguiente, se muestran varias maneras de manipular filas y columnas <xref:System.Windows.Forms.DataGridView> mediante las propiedades de la clase <xref:System.Windows.Forms.DataGridViewBand> de la que derivan las clases <xref:System.Windows.Forms.DataGridViewRow> y <xref:System.Windows.Forms.DataGridViewColumn>.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Windows.Forms.DataGridView.ButtonDemos#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CPP/DataGridViewBandDemo.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ButtonDemos#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CS/DataGridViewBandDemo.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ButtonDemos#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/VB/datagridviewbanddemo.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewBand>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Programar con celdas, filas y columnas en el control DataGridView de Windows Forms](programming-with-cells-rows-and-columns-in-the-datagrid.md)
