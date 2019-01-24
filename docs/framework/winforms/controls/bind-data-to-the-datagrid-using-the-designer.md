---
title: Procedimiento Enlazar datos con el Control de DataGridView de Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: 51f190618c71731aad722b93562a01a4dc7b9b34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558220"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Procedimiento Enlazar datos con el Control de DataGridView de Windows Forms mediante el diseñador
Puede utilizar el diseñador para conectar un <xref:System.Windows.Forms.DataGridView> control a orígenes de datos de diferentes variedades, incluidas las bases de datos, objetos de negocio o servicios Web. Al enlazar el control a un origen de datos mediante el diseñador, el control se enlaza automáticamente a un <xref:System.Windows.Forms.BindingSource> componente que representa el origen de datos. Además, las columnas se generan automáticamente en el control para coincidir con la información del esquema proporcionada por el origen de datos.  
  
 Después de generar las columnas, puede modificarlas para satisfacer sus necesidades. Por ejemplo, puede quitar u ocultar aquellas columnas que no desee mostrar, puede reorganizar las columnas o puede modificar los tipos de columna. Para más información sobre la modificación de columnas, consulte los temas mostrados en la sección Vea también.  
  
 También puede enlazar varios <xref:System.Windows.Forms.DataGridView> controles a las tablas relacionadas para crear relaciones principal/detalle. En esta configuración, un control muestra una tabla primaria y otro control muestra solo aquellas filas de una tabla secundaria que están relacionadas con la fila actual de la tabla primaria. Para obtener más información, vea [Cómo: Mostrar relacionados con datos en un Windows Forms Application](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
 El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contiene un <xref:System.Windows.Forms.DataGridView> control o dos controles de una relación principal-detalle. Para obtener información acerca de cómo iniciar tal proyecto, vea [Cómo: Cree un proyecto de aplicación Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-bind-the-control-to-a-data-source"></a>Para enlazar el control a un origen de datos  
  
1.  Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control.  
  
2.  Haga clic en la flecha de lista desplegable de la opción **Elegir origen de datos**.  
  
3.  Si su proyecto aún no tiene un origen de datos, haga clic en **Agregar origen de datos del proyecto** y siga los pasos indicados por el asistente.  
  
     Para más información, consulte [Asistente para la configuración de orígenes de datos](https://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f). El nuevo origen de datos aparecerá en la ventana desplegable **Elegir origen de datos**. Si el nuevo origen de datos contiene solo un miembro, como una única tabla de base de datos, el control se enlazará automáticamente a dicho miembro. De lo contrario, vaya al paso siguiente.  
  
4.  Expanda los nodos **Otros orígenes de datos** y **Orígenes de datos del proyecto** si aún no están expandidos y, después, seleccione el origen datos al que desea enlazar el control.  
  
5.  Si el origen de datos contiene más de un miembro, por ejemplo, si ha creado un <xref:System.Data.DataSet?displayProperty=nameWithType> que contiene varias tablas, expanda el origen de datos y, a continuación, seleccione el miembro específico para enlazar a.  
  
6.  Para crear una relación principal/detalle, en el **Elegir origen de datos** ventana desplegable durante un segundo <xref:System.Windows.Forms.DataGridView> controlar, expanda el <xref:System.Windows.Forms.BindingSource> creado para la tabla primaria y, a continuación, seleccione la tabla secundaria relacionada en la lista se muestra.  
  
    > [!NOTE]
    >  Si el proyecto ya tiene un origen de datos, también puede usar la ventaja **Orígenes de datos** para crear un formulario de datos. Para más información, consulte [Orígenes de datos (ventana)](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- [Cómo: Conectarse a datos en una base de datos](https://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)
- [Cómo: Agregar y quitar columnas en el Control de DataGridView de Windows Forms mediante el diseñador](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Cambiar el orden de columnas en el Control de DataGridView de Windows Forms mediante el diseñador](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Cambiar el tipo de una columna DataGridView de Windows Forms mediante el diseñador](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [Cómo: Inmovilizar columnas en el Control de DataGridView de Windows Forms mediante el diseñador](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Ocultar columnas en el Control de DataGridView de Windows Forms mediante el diseñador](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)
- [Cómo: Que las columnas de sólo lectura en el Control de DataGridView de Windows Forms mediante el diseñador](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [Cómo: crear un proyecto de aplicación para Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)
- [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
- [Ventana Orígenes de datos](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)
- [Cómo: Mostrar datos relacionados en una aplicación de Windows Forms](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
