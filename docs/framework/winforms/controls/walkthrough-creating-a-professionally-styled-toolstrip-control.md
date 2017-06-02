---
title: "Tutorial: Crear un control ToolStrip de estilo profesional | Microsoft Docs"
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
  - "barras de herramientas [Windows Forms], tutoriales"
  - "ToolStrip (control) [Windows Forms], crear controles con estilo profesional"
  - "ToolStripProfessionalRenderer (clase) [Windows Forms]"
  - "ToolStripRenderer (clase) [Windows Forms]"
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Tutorial: Crear un control ToolStrip de estilo profesional
Puede dar a los controles <xref:System.Windows.Forms.ToolStrip> de la aplicación un aspecto y comportamiento profesional escribiendo su propia clase derivada del tipo <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
 Este tutorial muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStrip> para crear un control compuesto que se parezca al **Panel de navegación** incluido en Microsoft® Outlook®.  En este tutorial se muestran las tareas siguientes:  
  
-   Crear un nuevo proyecto de Biblioteca de controles de Windows.  
  
-   Diseñar el control StackView.  
  
-   Implementar un representador personalizado.  
  
 Cuando finalice, tendrá un control de cliente personalizado reutilizable con el aspecto profesional de un control de Microsoft Office® XP.  
  
 Para copiar el código de este tema como un listado sencillo, vea [Cómo: Crear un control ToolStrip de estilo profesional](../../../../docs/framework/winforms/controls/how-to-create-a-professionally-styled-toolstrip-control.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos necesarios para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde esté instalado [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
## Crear un nuevo proyecto de Biblioteca de controles de Windows  
 El primer paso es crear el proyecto de Biblioteca de controles.  
  
#### Para crear el proyecto de Biblioteca de controles  
  
1.  Cree un nuevo proyecto de Biblioteca de controles de Windows denominado `StackViewLibrary`.  
  
2.  En el **Explorador de soluciones**, elimine el control predeterminado del proyecto eliminando el archivo de código fuente denominado "UserControl1.cs" o "UserControl1.vb", dependiendo del lenguaje elegido.  
  
     Para obtener más información, vea [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/es-es/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).  
  
3.  Agregue un nuevo elemento <xref:System.Windows.Forms.UserControl> al proyecto **StackViewLibrary**.  Dé el nombre base de `StackView` al nuevo archivo de código fuente.  
  
## Diseñar el control StackView  
 El control `StackView` es un control compuesto de un control <xref:System.Windows.Forms.ToolStrip> secundario.  Para obtener más información acerca de los controles compuestos, vea [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).  
  
#### Para diseñar el control StackView  
  
1.  En el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.ToolStrip> a la superficie de diseño.  
  
2.  En la ventana **Propiedades**, establezca las propiedades del control <xref:System.Windows.Forms.ToolStrip> de acuerdo con la tabla siguiente.  
  
    |Propiedad.|Valor|  
    |----------------|-----------|  
    |Name|`stackStrip`|  
    |CanOverflow|`false`|  
    |Dock|<xref:System.Windows.Forms.DockStyle>|  
    |Fuente|`Tahoma, 10pt, style=Bold`|  
    |GripStyle|<xref:System.Windows.Forms.ToolStripGripStyle>|  
    |LayoutStyle|<xref:System.Windows.Forms.ToolStripLayoutStyle>|  
    |Relleno|`0, 7, 0, 0`|  
    |RenderMode|<xref:System.Windows.Forms.ToolStripRenderMode>|  
  
3.  En el Diseñador de Windows Forms, haga clic en el botón **Agregar** del control <xref:System.Windows.Forms.ToolStrip> y agregue <xref:System.Windows.Forms.ToolStripButton> al control `stackStrip`.  
  
4.  En la ventana **Propiedades**, establezca las propiedades del control <xref:System.Windows.Forms.ToolStripButton> de acuerdo con la tabla siguiente.  
  
    |Propiedad.|Valor|  
    |----------------|-----------|  
    |Name|`mailStackButton`|  
    |CheckOnClick|true|  
    |CheckState|<xref:System.Windows.Forms.CheckState>|  
    |DisplayStyle|<xref:System.Windows.Forms.ToolStripItemDisplayStyle>|  
    |ImageAlign|<xref:System.Drawing.ContentAlignment>|  
    |ImageScaling|<xref:System.Windows.Forms.ToolStripItemImageScaling>|  
    |ImageTransparentColor|`238, 238, 238`|  
    |Margin|`0, 0, 0, 0`|  
    |Relleno|`3, 3, 3, 3`|  
    |Text|Mail|  
    |TextAlign|<xref:System.Drawing.ContentAlignment>|  
  
5.  Repita el paso 7 para tres controles <xref:System.Windows.Forms.ToolStripButton> más.  
  
     Los nombres de los controles son `calendarStackButton`, `contactsStackButton` y `tasksStackButton`.  Establezca el valor de la propiedad <xref:System.Windows.Forms.Control.Text%2A> en Calendar, Contacts y Tasks, respectivamente.  
  
## Controlar eventos  
 Dos eventos son importantes para hacer que el control `StackView` se comporte correctamente.  Controle el evento <xref:System.Windows.Forms.UserControl.Load> para colocar el control correctamente.  Controle el evento <xref:System.Windows.Forms.ToolStripItem.Click> de cada <xref:System.Windows.Forms.ToolStripButton> para asignar al control `StackView` un comportamiento de estado similar al control <xref:System.Windows.Forms.RadioButton>.  
  
#### Para controlar eventos  
  
1.  En el Diseñador de Windows Forms, seleccione el control `StackView`.  
  
2.  En la ventana **Propiedades**, haga clic en el botón **Eventos**.  
  
3.  Haga doble clic en el evento Load para generar el controlador de eventos `StackView_Load`.  
  
4.  En el controlador de eventos `StackView_Load`, copie y pegue el siguiente código:  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  En el Diseñador de Windows Forms, seleccione el control `mailStackButton`.  
  
6.  En la ventana **Propiedades**, haga clic en el botón **Eventos**.  
  
7.  Haga doble clic en el evento Click.  
  
     El Diseñador de Windows Forms genera el controlador de eventos `mailStackButton_Click`.  
  
8.  Cambie el nombre del controlador de eventos `mailStackButton_Click` a `stackButton_Click`.  
  
     Para obtener más información, vea [How to: Rename an Identifier \(Visual Basic\)](http://msdn.microsoft.com/es-es/e5a5edf8-3dba-4119-81f4-fc2aba180e0c).  
  
9. Inserte el código siguiente en el controlador de eventos `stackButton_Click`.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. En el Diseñador de Windows Forms, seleccione el control `calendarStackButton`.  
  
11. En la ventana **Propiedades**, establezca el evento Click en el controlador de eventos `stackButton_Click`.  
  
12. Repita los pasos 10 y 11 con los controles `contactsStackButton` y `tasksStackButton`.  
  
## Definir iconos  
 Cada botón `StackView` tiene un icono asociado.  Por comodidad, cada icono se representa como una cadena codificada en base64, que se deserializa antes de que se cree un <xref:System.Drawing.Bitmap> a partir de él.  En un entorno de producción, los datos del mapa de bits se almacenan como un recurso y sus iconos aparecen en el Diseñador de Windows Forms.  Para obtener más información, vea [How to: Add Background Images to Windows Forms](http://msdn.microsoft.com/es-es/7a509ba2-055c-4ae6-b88a-54625c6d9aff).  
  
#### Para definir los iconos  
  
1.  En el Editor de código, inserte el siguiente código en la definición de clase `StackView`.  Este código inicializa los mapas de bits de los iconos <xref:System.Windows.Forms.ToolStripButton>.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  Agregue una llamada al método `InitializeImages` en el constructor de clase `StackView`.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## Implementar un representador personalizado  
 Puede personalizar la mayoría de los elementos del control `StackView` implementando una clase que deriva de la clase <xref:System.Windows.Forms.ToolStripRenderer>.  En este procedimiento, implementará una clase <xref:System.Windows.Forms.ToolStripProfessionalRenderer> que personaliza el control y dibuja los fondos del degradado de los controles <xref:System.Windows.Forms.ToolStripButton>.  
  
#### Para implementar un representador personalizado  
  
1.  Inserte el código siguiente en definición del control `StackView`.  
  
     Ésta es la definición de la clase `StackRenderer`, que reemplaza a <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder> y a los métodos <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> para generar un aspecto personalizado.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  En el constructor del control `StackView`, cree una nueva instancia de la clase `StackRenderer` y asigne esta instancia a la propiedad <xref:System.Windows.Forms.ToolStrip.Renderer%2A> del control `stackStrip`.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## Probar el control StackView  
 El control `StackView` deriva de la clase <xref:System.Windows.Forms.UserControl>.  Por consiguiente, puede probar el control con **UserControl Test Container**.  Para obtener más información, vea [Cómo: Comprobar el comportamiento de un control de usuario en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
#### Para probar el control StackView  
  
1.  Presione F5 para compilar el proyecto e iniciar **UserControl Test Container**.  
  
2.  Mueva el puntero sobre los botones del control `StackView` y, a continuación, haga clic en un botón para ver el aspecto de su estado seleccionado.  
  
## Pasos siguientes  
 En este tutorial, ha creado un control de cliente personalizado reutilizable con el aspecto profesional de un control de Office XP.  Puede utilizar la familia <xref:System.Windows.Forms.ToolStrip> de controles para muchos otros propósitos:  
  
-   Crear menús contextual para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.  Para obtener más información, vea [Información general sobre ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Crear un formulario con un menú estándar rellenado automáticamente.  Para obtener más información, vea [Tutorial: Proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Crear un formulario de interfaz de múltiples documentos \(MDI\) con controles <xref:System.Windows.Forms.ToolStrip> acoplados.  Para obtener más información, vea [Cómo: Crear un formulario MDI con combinación de menús y controles ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [Cómo: Proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)