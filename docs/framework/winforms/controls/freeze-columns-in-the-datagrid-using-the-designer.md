---
title: Filtrar para inmovilizar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: 437e49a1f8e5a154f1a54fc7a266579cb5f0122c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100007"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Filtrar para inmovilizar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador
Cuando los usuarios ven los datos mostrados en un control <xref:System.Windows.Forms.DataGridView> de Windows Forms, a veces deben hacer referencia a una sola columna o a un conjunto de columnas con frecuencia. Por ejemplo, cuando se muestra una tabla de información de cliente que contiene muchas columnas, es útil para mostrar el nombre del cliente en todo momento, mientras que otras columnas puedan desplazarse fuera del área visible.  
  
 Para conseguir este comportamiento, puede inmovilizar las columnas en el control. Al inmovilizar una columna, también se inmovilizan todas las columnas situadas a su izquierda (o a su derecha en los scripts de idioma de derecha a izquierda). Las columnas inmovilizadas permanecen en su lugar mientras que todas las demás columnas se pueden desplazar. Si se habilita la reordenación de columnas, las columnas inmovilizadas se tratan como un grupo distinto de las columnas no inmovilizadas. Los usuarios pueden cambiar la ubicación de las columnas en los grupos, pero no pueden mover una columna de un grupo a otro.  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-freeze-a-column-using-the-designer"></a>Para inmovilizar una columna mediante el diseñador  
  
1.  Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Editar columnas**.  
  
2.  Seleccione una columna en la **columnas seleccionadas** lista.  
  
3.  En el **propiedades de columna** cuadrícula, establecer el <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> propiedad `true`.  
  
    > [!NOTE]
    >  También puede inmovilizar una columna al agregarla seleccionando el **congeladas** cuadro el **Agregar columna** cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [Filtrar para agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el diseñador](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Filtrar para habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms mediante el diseñador](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- [Filtrar Mostrar texto de derecha a izquierda en formularios de Windows para la globalización](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))
- [Filtrar Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Filtrar para agregar controles a formularios Windows Forms](how-to-add-controls-to-windows-forms.md)
