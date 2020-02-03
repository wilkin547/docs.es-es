---
title: Cambiar mediante programación el tamaño de las celdas para ajustar el contenido en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells to fit content
- cells [Windows Forms], resizing to fit contents
- DataGridView control [Windows Forms], resizing cells
- grids [Windows Forms], resizing cells to fit content
ms.assetid: 63d770dc-b3f5-462b-901a-3125b2753792
ms.openlocfilehash: df3b378a8ba358fa0bfe549a7901b3d59d53f556
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742452"
---
# <a name="how-to-programmatically-resize-cells-to-fit-content-in-the-windows-forms-datagridview-control"></a>Cómo: Cambiar mediante programación el tamaño de las celdas para ajustar el contenido en el control DataGridView de formularios Windows Forms
Puede usar los métodos <xref:System.Windows.Forms.DataGridView> del control para cambiar el tamaño de las filas, columnas y encabezados para que muestren sus valores completos sin truncarlos. Puede usar estos métodos para cambiar el tamaño de los elementos <xref:System.Windows.Forms.DataGridView> cuando elija. También puede configurar el control para cambiar el tamaño de estos elementos automáticamente cada vez que cambie el contenido. Sin embargo, esto puede resultar poco eficiente si trabaja con grandes conjuntos de datos o si los datos cambian con frecuencia. Para obtener más información, consulte [Opciones de ajuste de tamaño en el control DataGridView Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
 Normalmente, ajustará los elementos <xref:System.Windows.Forms.DataGridView> mediante programación para ajustar su contenido solo cuando cargue nuevos datos de un origen de datos o cuando el usuario edite un valor. Esto es útil para optimizar el rendimiento, pero también es útil si quiere permitir que los usuarios cambien manualmente el tamaño de las filas y columnas con el mouse.  
  
 El ejemplo de código siguiente muestra las opciones disponibles para cambiar el tamaño mediante programación.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CPP/programmaticsizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/CS/programmaticsizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.ProgrammaticResizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ProgrammaticResizing/VB/programmaticsizing.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeColumnHeadersHeight%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRow%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRows%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoResizeRowHeadersWidth%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Cambiar el tamaño de columnas y filas en el control DataGridView de Windows Forms](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Cambiar automáticamente el tamaño de las celdas cuando se modifica el contenido en un control DataGridView de formularios Windows Forms](automatically-resize-cells-when-content-changes-in-the-datagrid.md)
