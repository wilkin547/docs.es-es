---
title: 'Cómo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador'
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: f98d0e530f502655b9a48819d266a604581d22de
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528150"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador
Los formularios Windows Forms <xref:System.Windows.Forms.DataGridView> control debe contener las columnas para mostrar los datos. Si tiene previsto rellenar el control manualmente, debe agregar las columnas. Como alternativa, puede enlazar el control a un origen de datos, que genera y rellena las columnas automáticamente. Si el origen de datos contiene más columnas de las que desea mostrar, puede quitar las columnas innecesarias.  
  
 Los procedimientos siguientes requieren un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-column-using-the-designer"></a>Para agregar una columna mediante el diseñador  
  
1.  Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control y, a continuación, seleccione **Agregar columna**.  
  
2.  En el **Agregar columna** diálogo cuadro, elija la **columna enlazada a datos** opción y seleccione una columna del origen de datos o elija la **columna sin enlazar** opción y definir la columna uso de los campos correspondientes.  
  
3.  Haga clic en el **agregar** botón para agregar la columna, provocando que aparecen en el diseñador si las columnas existentes no han rellenan el área de presentación del control.  
  
    > [!NOTE]
    >  Puede modificar las propiedades de columna en la **Editar columnas** cuadro de diálogo que se puede acceder desde la etiqueta inteligente del control.  
  
### <a name="to-remove-a-column-using-the-designer"></a>Para quitar una columna mediante el diseñador  
  
1.  Elija **Editar columnas** de etiquetas inteligentes del control.  
  
2.  Seleccione una columna en la **columnas seleccionadas** lista.  
  
3.  Haga clic en el **quitar** botón para eliminar la columna, haciendo que desaparezca desde el diseñador.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
