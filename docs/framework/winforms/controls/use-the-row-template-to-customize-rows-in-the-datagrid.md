---
title: 'Cómo: Utilizar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 2bde9b3f6934833804866e29c18f3636c65ba069
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Cómo: Utilizar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control usa la plantilla de fila como base para todas las filas que agregan al control a través del enlace de datos o cuando se llama a la <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> método sin especificar una fila existente para usar.  
  
 La plantilla de filas ofrece un mayor control sobre la apariencia y comportamiento de filas que la <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> proporciona la propiedad. Con la plantilla de fila, puede establecer cualquier <xref:System.Windows.Forms.DataGridViewRow> propiedades, incluyendo <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 Existen algunas situaciones donde debe usar la plantilla de fila para lograr un efecto determinado. Por ejemplo, no se puede almacenar información de alto de fila en un <xref:System.Windows.Forms.DataGridViewCellStyle>, por lo que deberá usar una plantilla de fila para cambiar el alto predeterminado utilizado por todas las filas. La plantilla de fila también es útil al crear sus propias clases derivadas de <xref:System.Windows.Forms.DataGridViewRow> y desea que el tipo personalizado que se usa cuando se agregan nuevas filas al control.  
  
> [!NOTE]
>  La plantilla de fila se utiliza únicamente cuando se agregan filas. No se puede cambiar las filas existentes cambiando la plantilla de fila.  
  
### <a name="to-use-the-row-template"></a>Para usar la plantilla de fila  
  
-   Establecer propiedades en el objeto recuperado desde el <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> propiedad.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>  
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Estilos de celda en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
