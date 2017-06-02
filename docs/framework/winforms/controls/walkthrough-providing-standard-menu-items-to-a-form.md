---
title: "Tutorial: Proporcionar elementos de men&#250; est&#225;ndar a un formulario | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "elementos de menú, estándar"
  - "StatusStrip (control) [Windows Forms]"
  - "barras de herramientas [Windows Forms], tutoriales"
  - "ToolStrip (control) [Windows Forms]"
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Tutorial: Proporcionar elementos de men&#250; est&#225;ndar a un formulario
Puede proporcionar un menú estándar a los formularios con el control <xref:System.Windows.Forms.MenuStrip>.  
  
 Este tutorial muestra cómo utilizar un control <xref:System.Windows.Forms.MenuStrip> para crear un menú estándar.  El formulario también responde cuando un usuario selecciona un elemento de menú.  En este tutorial se muestran las tareas siguientes:  
  
-   Crear un proyecto de formularios Windows Forms.  
  
-   Crear un menú estándar.  
  
-   Crear un control <xref:System.Windows.Forms.StatusStrip>.  
  
-   Controlar la selección de elementos de menú.  
  
 Cuando termine, tendrá un formulario con un menú estándar que muestra las selecciones de elementos de menú en un control <xref:System.Windows.Forms.StatusStrip>.  
  
 Para copiar el código de este tema como un listado sencillo, vea [Cómo: Proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos necesarios para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde esté instalado [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
## Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### Para crear el proyecto  
  
1.  Cree un proyecto de aplicación para Windows denominado StandardMenuForm.  
  
     Para obtener más información, consulte [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  En el Diseñador de Windows Forms, seleccione el formulario.  
  
## Crear un menú estándar  
 El Diseñador de Windows Forms puede rellenar automáticamente un control <xref:System.Windows.Forms.MenuStrip> con elementos de menú estándar.  
  
#### Para crear un menú estándar  
  
1.  En el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.MenuStrip> hasta el formulario.  
  
2.  Haga clic en el glifo \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) de etiqueta inteligente del control <xref:System.Windows.Forms.MenuStrip> y seleccione **Insertar elementos estándar**.  
  
     Se rellenará el control <xref:System.Windows.Forms.MenuStrip> con los elementos de menú estándar.  
  
3.  Haga clic en el elemento de menú **Archivo** para ver sus elementos de menú predeterminados y los iconos correspondientes.  
  
## Crear un control StatusStrip  
 Utilice el control <xref:System.Windows.Forms.StatusStrip> para mostrar el estado de las aplicaciones de Windows Forms.  En el ejemplo actual, los elementos de menú seleccionados por el usuario se muestran en un control <xref:System.Windows.Forms.StatusStrip>.  
  
#### Para crear un control StatusStrip  
  
1.  En el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.StatusStrip> hasta el formulario.  
  
     Se acoplará automáticamente el control <xref:System.Windows.Forms.StatusStrip> a la parte inferior del formulario.  
  
2.  Haga clic en el botón de lista desplegable del control <xref:System.Windows.Forms.StatusStrip> y seleccione **StatusLabel** para agregar un control <xref:System.Windows.Forms.ToolStripStatusLabel> al control <xref:System.Windows.Forms.StatusStrip>.  
  
## Controlar la selección de elementos  
 Controle el evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> para que responda cuando el usuario seleccione un elemento de menú.  
  
#### Para controlar la selección de elementos  
  
1.  Haga clic en el elemento de menú **Archivo** que creó en la sección Crear un menú estándar.  
  
2.  En la ventana **Propiedades**, haga clic en el botón **Eventos**.  
  
3.  Haga doble clic en el evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.  
  
     El Diseñador de Windows Forms generará un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked>.  
  
4.  Inserte el código siguiente en el controlador de eventos.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  Inserte la definición de método de utilidad `UpdateStatus` en el formulario.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## Punto de control  
  
#### Para probar el formulario  
  
1.  Presione F5 para compilar y ejecutar el formulario.  
  
2.  Haga clic en el elemento de menú **Archivo** para abrir el menú.  
  
3.  En el menú **Archivo**, haga clic en uno de los elementos para seleccionarlo.  
  
     Se mostrará en el control <xref:System.Windows.Forms.StatusStrip> el elemento seleccionado.  
  
## Pasos siguientes  
 En este tutorial, ha creado un formulario con un menú estándar.  Puede utilizar la familia <xref:System.Windows.Forms.ToolStrip> de controles para muchos otros propósitos:  
  
-   Crear menús contextual para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.  Para obtener más información, vea [Información general sobre ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Crear un formulario de interfaz de múltiples documentos \(MDI\) con controles <xref:System.Windows.Forms.ToolStrip> acoplados.  Para obtener más información, vea [Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
-   Proporcionar a los controles <xref:System.Windows.Forms.ToolStrip> un aspecto profesional.  Para obtener más información, vea [Cómo: Establecer la representación de ToolStrip para una aplicación](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)