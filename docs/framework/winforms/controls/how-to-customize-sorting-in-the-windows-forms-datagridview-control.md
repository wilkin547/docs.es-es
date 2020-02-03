---
title: Personalizar la ordenación en un control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], sorting
- data grids [Windows Forms], customizing sorting
ms.assetid: 92fb5c14-afab-4cf5-a97e-924fd9cb99f5
ms.openlocfilehash: 20f581b2df6fd172a0a1998aed60c56b0306f2eb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743179"
---
# <a name="how-to-customize-sorting-in-the-windows-forms-datagridview-control"></a>Cómo: Personalizar la ordenación en el control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> proporciona ordenación automática pero, dependiendo de sus necesidades, puede que necesite personalizar las operaciones de ordenación. Por ejemplo, puede usar la ordenación mediante programación para crear una interfaz de usuario alternativa. También puede controlar el evento <xref:System.Windows.Forms.DataGridView.SortCompare> o llamar a la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> para disfrutar de más opciones de ordenación, como la ordenación de varias columnas.  
  
 Los ejemplos de código siguientes muestran estos tres enfoques de la ordenación personalizada. Para más información, consulte [Modos de ordenación de columnas del control DataGridView de Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md).  
  
## <a name="programmatic-sorting"></a>Ordenación mediante programación  
 En el ejemplo de código siguiente se muestra una ordenación mediante programación usando las propiedades <xref:System.Windows.Forms.DataGridView.SortOrder%2A> y <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> para determinar la dirección de la ordenación, y la propiedad <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A> para establecer manualmente el glifo de ordenación. La sobrecarga `Sort(DataGridViewColumn,ListSortDirection)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> se usa para ordenar los datos de una sola columna.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewProgrammaticSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewProgrammaticSort/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-sortcompare-event"></a>Ordenación personalizada mediante el evento SortCompare  
 En el ejemplo de código siguiente se muestra la ordenación personalizada mediante un controlador de eventos <xref:System.Windows.Forms.DataGridView.SortCompare>. Se ordena la <xref:System.Windows.Forms.DataGridViewColumn> seleccionada y, si hay valores duplicados en la columna, se usa el identificador de columna para determinar el orden final.  
  
 [!code-csharp[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.SortCompare#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.SortCompare/VB/form1.vb#00)]  
  
## <a name="custom-sorting-using-the-icomparer-interface"></a>Ordenación personalizada mediante la interfaz IComparer  
 En el ejemplo de código siguiente se muestra la ordenación personalizada mediante la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A>, que toma una implementación de la interfaz <xref:System.Collections.IComparer> para realizar una ordenación de varias columnas.  
  
 [!code-csharp[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/CS/form1.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewIComparerSort#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewIComparerSort/VB/form1.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Estos ejemplos requieren:  
  
- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- [Ordenar datos en el control DataGridView de Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Modos de ordenación de columnas del control DataGridView de Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Cómo: Establecer modos de ordenación de columnas en el control DataGridView de Windows Forms](set-the-sort-modes-for-columns-wf-datagridview-control.md)
