---
title: Procedimiento para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: a735b9bef9f9e3488941e05b2aa9444e6ecdc4b8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012885"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a>Procedimiento para crear columnas de solo lectura en el control DataGridView de formularios Windows Forms mediante el diseñador
De forma predeterminada, los usuarios pueden modificar texto y datos numéricos que se muestra en los formularios de Windows <xref:System.Windows.Forms.DataGridView> control. Si desea mostrar los datos que no está diseñados para su modificación, debe realizar las columnas que contienen los datos de solo lectura. Para obtener información acerca de cómo hacer que el control sea de sólo lectura, vea [Cómo: Impedir la adición de la fila y la eliminación en la Windows Forms Control DataGridView de formularios mediante el diseñador](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-make-a-column-read-only-by-using-the-designer"></a>Convertir una columna de solo lectura mediante el diseñador  
  
1. Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Editar columnas**.  
  
2. Seleccione una columna en la **columnas seleccionadas** lista.  
  
3. En el **propiedades de columna** cuadrícula, establecer el <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> propiedad `true`.  
  
    > [!NOTE]
    >  Puede hacer también una columna de sólo lectura cuando se agrega al seleccionar el **de sólo lectura** casilla de verificación en la **Agregar columna** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Cómo: Agregar y quitar columnas en el Control de DataGridView de Windows Forms mediante el diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Impedir la adición de fila y eliminación en el Control de DataGridView de Windows Forms mediante el diseñador](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- [Cómo: Crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
