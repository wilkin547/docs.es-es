---
title: Usar la plantilla de filas para personalizar filas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 35cb95f22c0caa654bf149b5fc4fd0395696a411
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728384"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Cómo: Utilizar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> usa la plantilla de fila como base para todas las filas que se agregan al control mediante el enlace de datos o cuando se llama al método <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> sin especificar una fila existente que se va a usar.  
  
 La plantilla de fila proporciona un mayor control sobre la apariencia y el comportamiento de las filas que proporciona la propiedad <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>. Con la plantilla de fila, puede establecer cualquier <xref:System.Windows.Forms.DataGridViewRow> propiedades, incluidas <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 Hay algunas situaciones en las que debe usar la plantilla de fila para lograr un efecto determinado. Por ejemplo, la información de alto de fila no se puede almacenar en un <xref:System.Windows.Forms.DataGridViewCellStyle>, por lo que debe usar una plantilla de fila para cambiar el alto predeterminado que usan todas las filas. La plantilla de fila también es útil cuando crea sus propias clases derivadas de <xref:System.Windows.Forms.DataGridViewRow> y desea que el tipo personalizado se use cuando se agreguen nuevas filas al control.  
  
> [!NOTE]
> La plantilla de fila solo se usa cuando se agregan filas. No se pueden cambiar las filas existentes cambiando la plantilla de fila.  
  
### <a name="to-use-the-row-template"></a>Para usar la plantilla de fila  
  
- Establezca las propiedades en el objeto recuperado de la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Estilo y formato básicos del control DataGridView en formularios Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
