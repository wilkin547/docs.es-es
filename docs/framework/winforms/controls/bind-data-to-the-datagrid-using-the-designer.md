---
title: "C&#243;mo: Enlazar datos al control DataGridView de formularios Windows Forms mediante el dise&#241;ador | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "orígenes de datos, enlazar a controles de formularios Windows Forms"
  - "DataGridView (control) [Windows Forms], enlace de datos"
  - "controles de Windows Forms, enlazar a orígenes de datos"
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# C&#243;mo: Enlazar datos al control DataGridView de formularios Windows Forms mediante el dise&#241;ador
Puede utilizar el diseñador para conectar un control <xref:System.Windows.Forms.DataGridView> a distintos orígenes de datos, incluso bases de datos, objetos de negocio o servicios Web.  Cuando enlaza el control a un origen de datos mediante el diseñador, el control se enlaza automáticamente a un componente <xref:System.Windows.Forms.BindingSource> que representa el origen de datos.  Además, las columnas se generan automáticamente en el control para coincidir con la información del esquema proporcionada por el origen de datos.  
  
 Después de generar las columnas, puede modificarlas para satisfacer sus necesidades.  Por ejemplo, puede quitar u ocultar aquellas columnas que no desee mostrar, puede reorganizar las columnas o puede modificar los tipos de columna.  Para obtener más información sobre la modificación de columnas, consulte los temas mostrados en la sección Vea también.  
  
 También puede enlazar varios controles <xref:System.Windows.Forms.DataGridView> a las tablas relacionadas para crear relaciones principal\/detalle.  En esta configuración, un control muestra una tabla primaria y otro control muestra sólo aquellas filas de una tabla secundaria que están relacionadas con la fila actual de la tabla primaria.  Para obtener más información, vea [Cómo: Mostrar datos relacionados en una aplicación de Windows Forms](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md).  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGridView>o dos controles de una relación principal\/detalle.  Para obtener información sobre cómo iniciar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para enlazar el control a un origen de datos  
  
1.  Haga clic en el glifo de la etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) situado en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView>.  
  
2.  Haga clic en la flecha de lista desplegable de la opción **Elegir origen de datos**.  
  
3.  Si su proyecto aún no tiene un origen de datos, hace clic en **Agregar origen de datos del proyecto** y siga los pasos indicados por el asistente.  
  
     Para obtener más información, vea [Asistente para la configuración de orígenes de datos](../Topic/Data%20Source%20Configuration%20Wizard.md).  El nuevo origen de datos aparecerá en la ventana desplegable **Elegir origen de datos**.  Si el nuevo origen de datos contiene sólo uno miembro, por ejemplo, una tabla de base de datos única, el control se enlazará automáticamente a dicho miembro.  En caso contrario, continúe con el paso siguiente.  
  
4.  Expanda los nodos **Otros orígenes de datos** y **Orígenes de datos del proyecto** si ya no están expandidos y, a continuación, seleccione el origen datos que desee enlazar al control.  
  
5.  Si el origen de datos contiene más de un miembro, por ejemplo, si ha creado un <xref:System.Data.DataSet?displayProperty=fullName> que contiene varias tablas, expanda el origen de datos y, a continuación, seleccione el miembro específico que se va a enlazar.  
  
6.  Para crear una relación principal\/detalle, en la ventana desplegable **Elegir origen de datos** de un segundo control <xref:System.Windows.Forms.DataGridView>, expanda el <xref:System.Windows.Forms.BindingSource> creado para la tabla primaria y, a continuación, seleccione la tabla secundaria relacionada en la lista que se muestra.  
  
    > [!NOTE]
    >  Si su proyecto ya tiene un origen de datos, también puede utilizar la ventana **Orígenes de datos** para crear un formulario de datos.  Para obtener más información, vea [Orígenes de datos \(ventana\)](../Topic/Data%20Sources%20Window.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=fullName>   
 [Cómo: Conectarse a los datos de una base de datos](../Topic/How%20to:%20Connect%20to%20Data%20in%20a%20Database.md)   
 [Cómo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [Cómo: Cambiar el orden de las columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)   
 [Cómo: Cambiar el tipo de una columna DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)   
 [Cómo: Inmovilizar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)   
 [Cómo: Ocultar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)   
 [Cómo: Crear columnas de sólo lectura en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [Orígenes de datos \(ventana\)](../Topic/Data%20Sources%20Window.md)   
 [Cómo: Mostrar datos relacionados en una aplicación de Windows Forms](../Topic/How%20to:%20Display%20Related%20Data%20in%20a%20Windows%20Forms%20Application.md)