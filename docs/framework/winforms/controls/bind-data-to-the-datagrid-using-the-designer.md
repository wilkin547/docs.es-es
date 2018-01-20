---
title: "Cómo: Enlazar datos al control DataGridView de formularios Windows Forms mediante el diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3a3c7422bc83c7ee1f09bac05333799708cd2f2f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Cómo: Enlazar datos al control DataGridView de formularios Windows Forms mediante el diseñador
Puede utilizar el diseñador para conectar un <xref:System.Windows.Forms.DataGridView> control a orígenes de datos de diferentes tipos, incluidas las bases de datos, objetos comerciales o servicios Web. Al enlazar el control a un origen de datos mediante el diseñador, el control se enlaza automáticamente a un <xref:System.Windows.Forms.BindingSource> componente que representa el origen de datos. Además, las columnas se generan automáticamente en el control para coincidir con la información del esquema proporcionada por el origen de datos.  
  
 Después de generar las columnas, puede modificarlas para satisfacer sus necesidades. Por ejemplo, puede quitar u ocultar aquellas columnas que no desee mostrar, puede reorganizar las columnas o puede modificar los tipos de columna. Para más información sobre la modificación de columnas, consulte los temas mostrados en la sección Vea también.  
  
 También puede enlazar varios <xref:System.Windows.Forms.DataGridView> controles a las tablas relacionadas para crear relaciones principal-detalle. En esta configuración, un control muestra una tabla primaria y otro control muestra solo aquellas filas de una tabla secundaria que están relacionadas con la fila actual de la tabla primaria. Para más información, consulte [Cómo: Mostrar datos relacionados en una aplicación de Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
 El procedimiento siguiente requiere un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGridView> control o dos controles de una relación principal-detalle. Para información sobre cómo iniciar tal proyecto, vea [Cómo: Crear un proyecto de aplicación para Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-bind-the-control-to-a-data-source"></a>Para enlazar el control a un origen de datos  
  
1.  Haga clic en el glifo de etiqueta inteligente (![glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) en la esquina superior derecha de la <xref:System.Windows.Forms.DataGridView> control.  
  
2.  Haga clic en la flecha de lista desplegable de la opción **Elegir origen de datos**.  
  
3.  Si su proyecto aún no tiene un origen de datos, haga clic en **Agregar origen de datos del proyecto** y siga los pasos indicados por el asistente.  
  
     Para más información, consulte [Asistente para la configuración de orígenes de datos](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f). El nuevo origen de datos aparecerá en la ventana desplegable **Elegir origen de datos**. Si el nuevo origen de datos contiene solo un miembro, como una única tabla de base de datos, el control se enlazará automáticamente a dicho miembro. De lo contrario, vaya al paso siguiente.  
  
4.  Expanda los nodos **Otros orígenes de datos** y **Orígenes de datos del proyecto** si aún no están expandidos y, después, seleccione el origen datos al que desea enlazar el control.  
  
5.  Si el origen de datos contiene más de un miembro, por ejemplo, si ha creado un <xref:System.Data.DataSet?displayProperty=nameWithType> que contiene varias tablas, expanda el origen de datos y, a continuación, seleccione el miembro específico que se va a enlazar a.  
  
6.  Para crear una relación maestro y detalles, en la **Elegir origen de datos** ventana de lista desplegable para un segundo <xref:System.Windows.Forms.DataGridView> controlar, expanda el <xref:System.Windows.Forms.BindingSource> creado para la tabla primaria y, a continuación, seleccione la tabla secundaria relacionada de la lista se muestra.  
  
    > [!NOTE]
    >  Si el proyecto ya tiene un origen de datos, también puede usar la ventaja **Orígenes de datos** para crear un formulario de datos. Para más información, consulte [Orígenes de datos (ventana)](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 [Cómo: Conectarse a los datos de una base de datos](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)  
 [Agregar y quitar columnas en el control DataGridView de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [Cambiar el orden de las columnas en el control DataGridView de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 [Cambiar el tipo de una columna DataGridView de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 [Inmovilizar columnas en el control DataGridView de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 [Ocultar columnas en el control DataGridView de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 [Crear columnas de sólo lectura en el control DataGridView de Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Cómo: Agregar controles a Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Ventana Orígenes de datos](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)  
 [Cómo: Mostrar datos relacionados en una aplicación de Windows Forms](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
