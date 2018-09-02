---
title: 'Cómo: Crear columnas de sólo lectura en el control DataGridView de formularios Windows Forms mediante el Diseñador'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 5d9c978f69b2dcfd91c1af6e80391852ed69da12
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466853"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Crear columnas de sólo lectura en el control DataGridView de formularios Windows Forms mediante el Diseñador
De forma predeterminada, los usuarios pueden modificar texto y datos numéricos que se muestra en los formularios de Windows <xref:System.Windows.Forms.DataGridView> control. Si desea mostrar los datos que no está diseñados para su modificación, debe realizar las columnas que contienen los datos de solo lectura. Para obtener información acerca de cómo hacer que el control sea de sólo lectura, vea [Cómo: impedir la adición de fila y la eliminación de la Windows Forms DataGridView Control mediante el diseñador](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a>Convertir una columna de solo lectura mediante el diseñador  
  
1.  Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Editar columnas**.  
  
2.  Seleccione una columna en la **columnas seleccionadas** lista.  
  
3.  En el **propiedades de columna** cuadrícula, establecer el <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> propiedad `true`.  
  
    > [!NOTE]
    >  Puede hacer también una columna de sólo lectura cuando se agrega al seleccionar el **de sólo lectura** casilla de verificación en la **Agregar columna** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 [Agregar y quitar columnas en el control DataGridView de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 [Cómo: crear un proyecto de aplicación de Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
