---
title: Establecer estilos de fila alternos para el control DataGridView mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 74f65d03a359136de943f8a2937ed5e5f1e62519
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743050"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador

Los datos tabulares se suelen presentar en un formato de libro de contabilidad en el que las filas alternas tienen diferentes colores de fondo. Este formato permite a los usuarios saber fácilmente qué celdas están en cada fila, especialmente con tablas anchas que tienen muchas columnas.

Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar la información de estilo completa para las filas alternas. Puede usar características de estilo como el color de primer plano y la fuente, además del color de fondo, para diferenciar las filas alternas. Para obtener más información, vea [estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGridView>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="define-styles-for-alternating-rows"></a>Definir estilos para filas alternas

1. Seleccione el control <xref:System.Windows.Forms.DataGridView> en el diseñador.

2. En la ventana **propiedades** , haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>.

3. En el cuadro de diálogo **generador de CellStyle** , defina el estilo estableciendo las propiedades y use el panel de **vista previa** para confirmar las opciones. Los estilos que especifique se usan para todas las demás filas mostradas en el control, comenzando por la segunda.

4. Para definir estilos para las filas restantes, repita los pasos 2 y 3 con la propiedad <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>.

    > [!NOTE]
    > Las celdas se muestran mediante estilos heredados de varias propiedades. Para obtener más información sobre la herencia de estilos, vea [estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Estilo y formato básicos del control DataGridView en formularios Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Utilizar el Diseñador con el control DataGridView de formularios Windows Forms](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
