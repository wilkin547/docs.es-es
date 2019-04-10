---
title: Filtrar para establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: fb338a3616bc20542ec940db5977c4ffdab9654c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335633"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a>Filtrar para establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el diseñador
Datos tabulares a menudo se presentan en un formato de carta donde las filas alternas tienen distintos colores de fondo. Este formato permite a los usuarios saber fácilmente qué celdas están en cada fila, especialmente con tablas anchas que tienen muchas columnas.  
  
 Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar la información de estilo completa para las filas alternas. Puede usar las características de estilo, como el color de primer plano y la fuente, además del color de fondo, para diferenciar las filas alternas. Para obtener más información, consulte [estilos de celda en el DataGridView Control de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="define-styles-for-alternating-rows"></a>Definir estilos para las filas alternas  
  
1. Seleccione el <xref:System.Windows.Forms.DataGridView> control en el diseñador.  
  
2. En el **propiedades** ventana, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) junto a la <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> propiedad.  
  
3. En el **generador de CellStyle** definir el estilo estableciendo las propiedades de cuadro de diálogo y usar el **Preview** panel para confirmar las opciones seleccionadas. Los estilos que especifique se usan para todas las demás filas mostrado en el control, empezando por la segunda.  
  
4. Para definir estilos para las filas restantes, repita los pasos 2 y 3 con el <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> propiedad.  
  
    > [!NOTE]
    >  Se muestran las celdas con los estilos que se hereda de varias propiedades. Para obtener más información sobre la herencia de estilo, consulte [estilos de celda en el DataGridView Control de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Estilos de celda en el control DataGridView de formularios Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Estilo y formato básicos del control DataGridView en formularios Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Utilizar el Diseñador con el control DataGridView de formularios Windows Forms](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [Filtrar Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Filtrar para agregar controles a formularios Windows Forms](how-to-add-controls-to-windows-forms.md)
