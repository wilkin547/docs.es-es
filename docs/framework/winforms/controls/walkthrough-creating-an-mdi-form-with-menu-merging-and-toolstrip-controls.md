---
title: "Tutorial: Crear un formulario MDI con combinaci&#243;n de men&#250;s y controles ToolStrip | Microsoft Docs"
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
  - "formularios MDI"
  - "formularios MDI, crear"
  - "formularios MDI, tutoriales"
  - "MDI, crear formularios"
  - "formularios de interfaz de múltiples documentos"
  - "barras de herramientas [Windows Forms]"
  - "ToolStrip (control) [Windows Forms]"
  - "ToolStripPanel (control) [Windows Forms]"
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Tutorial: Crear un formulario MDI con combinaci&#243;n de men&#250;s y controles ToolStrip
El espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> admite aplicaciones de interfaz de múltiples documentos \(MDI\) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús.  Los formularios MDI también pueden utilizar controles <xref:System.Windows.Forms.ToolStrip>.  
  
 Este tutorial muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStripPanel> con un formulario MDI.  El formulario también admite la combinación de menús con menús secundarios.  En este tutorial se muestran las tareas siguientes:  
  
-   Crear un proyecto de formularios Windows Forms.  
  
-   Crear el menú principal del formulario.  El nombre real del menú varía.  
  
-   Agregar el control <xref:System.Windows.Forms.ToolStripPanel> al **Cuadro de herramientas**.  
  
-   Crear un formulario secundario.  
  
-   Organizar controles <xref:System.Windows.Forms.ToolStripPanel> por orden z  
  
 Cuando termine, dispondrá de un formulario MDI que admite la combinación de menús y controles <xref:System.Windows.Forms.ToolStrip> móviles.  
  
 Para copiar el código de este tema como un listado sencillo, vea [Cómo: Crear un formulario MDI con combinación de menús y controles ToolStrip](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos necesarios para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde esté instalado [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
## Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### Para crear el proyecto  
  
1.  Cree un proyecto de aplicación para Windows denominado MdiForm.  
  
     Para obtener más información, consulte [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  En el Diseñador de Windows Forms, seleccione el formulario.  
  
3.  En la ventana Propiedades, establezca el valor de <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.  
  
## Crear el menú principal  
 El formulario MDI principal contiene el menú principal.  El menú principal tiene un elemento de menú denominado **Ventana**.  Con el elemento de menú **Ventana**, puede crear formularios secundarios.  Los elementos de menú de los formularios secundarios se combinan en el menú principal.  
  
#### Para crear el menú principal  
  
1.  En el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.MenuStrip> hasta el formulario.  
  
2.  Agregue un objeto <xref:System.Windows.Forms.ToolStripMenuItem> al control <xref:System.Windows.Forms.MenuStrip> y asígnele el nombre Ventana.  
  
3.  Seleccione el control <xref:System.Windows.Forms.MenuStrip>.  
  
4.  En la ventana Propiedades, establezca el valor de la propiedad <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> en `ToolStripMenuItem1`.  
  
5.  Agregue un subelemento al elemento de menú **Ventana** y, a continuación, asígnele el nombre Nuevo.  
  
6.  En la ventana Propiedades, haga clic en **Eventos**.  
  
7.  Haga doble clic en el evento <xref:System.Windows.Forms.ToolStripItem.Click>.  
  
     El Diseñador de Windows Forms genera un controlador de eventos para el evento <xref:System.Windows.Forms.ToolStripItem.Click>.  
  
8.  Inserte el código siguiente en el controlador de eventos.  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## Agregar el control ToolStripPanel al Cuadro de herramientas  
 Cuando utiliza los controles <xref:System.Windows.Forms.MenuStrip> con un formulario MDI que debe tener el control <xref:System.Windows.Forms.ToolStripPanel>.  Debe agregar el control <xref:System.Windows.Forms.ToolStripPanel> al **Cuadro de herramientas** para incorporar el formulario MDI en el Diseñador de Windows Forms.  
  
#### Para agregar el control ToolStripPanel al Cuadro de herramientas  
  
1.  Abra el **Cuadro de herramientas** y haga clic en la ficha **Todos los formularios Windows Forms** para mostrar los controles de formularios Windows Forms disponibles.  
  
2.  Haga clic con el botón secundario para abrir el menú contextual y seleccione **Elegir elementos**.  
  
3.  En el cuadro de diálogo **Elegir elementos del cuadro de herramientas**, desplácese hacia abajo por la columna **Nombre** hasta que encuentre **ToolStripPanel**.  
  
4.  Active la casilla al lado de **ToolStripPanel** y, a continuación, haga clic en **Aceptar**.  
  
     Aparecerá el control <xref:System.Windows.Forms.ToolStripPanel> en el **Cuadro de herramientas**.  
  
## Crear un formulario secundario  
 En este procedimiento, definirá una clase de formulario secundario independiente que tiene su propio control <xref:System.Windows.Forms.MenuStrip>.  Los elementos de menú para este formulario se combinan con aquéllos del formulario principal.  
  
#### Para definir un formulario secundario  
  
1.  Agregue un nuevo formulario denominado `ChildForm` al proyecto.  
  
     Para obtener más información, vea [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/es-es/3d7bb25f-fd90-47cf-9378-fa0d764686c1).  
  
2.  En el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.MenuStrip> hasta el formulario secundario.  
  
3.  Haga clic en el glifo de etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) del control <xref:System.Windows.Forms.MenuStrip> y, a continuación, seleccione **Editar elementos**.  
  
4.  En el cuadro de diálogo **Editor de la colección de elementos**, agregue un nuevo objeto <xref:System.Windows.Forms.ToolStripMenuItem> denominado ChildMenuItem en el menú secundario.  
  
     Para obtener más información, vea [ToolStrip Items Collection Editor](http://msdn.microsoft.com/es-es/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).  
  
## Comprobar el formulario  
  
#### Para probar el formulario  
  
1.  Presione F5 para compilar y ejecutar el formulario.  
  
2.  Haga clic en el elemento de menú **Ventana** para abrir el menú y, a continuación, haga clic en **Nuevo**.  
  
     Se creará un nuevo formulario secundario en el área de cliente MDI del formulario.  Se combinará el menú del formulario secundario con el menú principal.  
  
3.  Cierre el formulario secundario.  
  
     Se quitará el menú del formulario secundario del menú principal.  
  
4.  Haga clic varias veces en **Nuevo**.  
  
     Se mostrarán automáticamente los formularios secundarios bajo el elemento de menú **Ventana** porque se asigna la propiedad <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> del control <xref:System.Windows.Forms.MenuStrip>.  
  
## Agregar compatibilidad con ToolStrip  
 En este procedimiento, agregará cuatro controles <xref:System.Windows.Forms.ToolStrip> al formulario MDI principal.  Cada control <xref:System.Windows.Forms.ToolStrip> se agrega dentro de un control <xref:System.Windows.Forms.ToolStripPanel>, que se acopla al borde del formulario.  
  
#### Para agregar controles ToolStrip al formulario MDI principal  
  
1.  En el **Cuadro de herramientas**, arrastre un control <xref:System.Windows.Forms.ToolStripPanel> hasta el formulario.  
  
2.  Con el control <xref:System.Windows.Forms.ToolStripPanel> seleccionado, haga doble clic en el control <xref:System.Windows.Forms.ToolStrip> del **Cuadro de herramientas**.  
  
     Se creará un control <xref:System.Windows.Forms.ToolStrip> en el control <xref:System.Windows.Forms.ToolStripPanel>.  
  
3.  Seleccione el control <xref:System.Windows.Forms.ToolStripPanel>.  
  
4.  En la ventana Propiedades, cambie el valor de la propiedad del control <xref:System.Windows.Forms.Control.Dock%2A> a <xref:System.Windows.Forms.DockStyle>.  
  
     El control <xref:System.Windows.Forms.ToolStripPanel> se acoplará al lateral izquierdo del formulario, bajo el menú principal.  El área de cliente MDI cambiará el tamaño para adaptarse al control <xref:System.Windows.Forms.ToolStripPanel>.  
  
5.  Repita del paso 1 al 4.  
  
     Acople el nuevo control <xref:System.Windows.Forms.ToolStripPanel> a la parte superior del formulario.  
  
     El control <xref:System.Windows.Forms.ToolStripPanel> se acoplará bajo el menú principal, pero a la derecha del primer control <xref:System.Windows.Forms.ToolStripPanel>.  Este paso muestra la importancia del orden z para colocar correctamente los controles <xref:System.Windows.Forms.ToolStripPanel>.  
  
6.  Repita los pasos del 1 al 4 para dos controles <xref:System.Windows.Forms.ToolStripPanel> más.  
  
     Acople los nuevos controles <xref:System.Windows.Forms.ToolStripPanel> al borde derecho e inferior del formulario.  
  
## Organizar los controles ToolStripPanel por orden z  
 La posición de un control <xref:System.Windows.Forms.ToolStripPanel> acoplado en el formulario MDI viene determinada por la posición del control en el orden z.  Puede organizar con facilidad el orden z de los controles en la ventana Esquema del documento.  
  
#### Para organizar los controles ToolStripPanel por orden z  
  
1.  En el menú **Ver**, haga clic en **Otras ventanas** y, a continuación, en **Esquema del documento**.  
  
     La disposición de los controles <xref:System.Windows.Forms.ToolStripPanel> del procedimiento anterior no es estándar.  Esto es porque el orden z no es correcto.  Utilice la ventana Esquema del documento para cambiar el orden z de los controles.  
  
2.  En la ventana Esquema del documento, seleccione **ToolStripPanel4**.  
  
3.  Haga clic repetidamente en el botón de flecha abajo hasta que **ToolStripPanel4** esté en la parte inferior de la lista.  
  
     El control **ToolStripPanel4** se acoplará a la parte inferior del formulario, bajo los otros controles.  
  
4.  Seleccione **ToolStripPanel2**.  
  
5.  Haga clic en el botón de flecha abajo un vez para colocar el control el tercero de la lista.  
  
     El control **ToolStripPanel2** se acoplará a la parte superior del formulario, bajo el menú principal y sobre los otros controles.  
  
6.  Seleccione los distintos controles de la ventana **Esquema del documento** y desplácelos a posiciones diferentes en el orden z.  Tenga en cuenta el efecto del orden z en la posición de controles acoplados.  Utilice CTRL\-Z o **Deshacer** en el menú **Editar** para deshacer los cambios.  
  
## Punto de control  
  
#### Para probar el formulario  
  
1.  Presione F5 para compilar y ejecutar el formulario.  
  
2.  Haga clic en el control de agarre de un control <xref:System.Windows.Forms.ToolStrip> y arrastre el control a posiciones diferentes en el formulario.  
  
     Puede arrastrar un control <xref:System.Windows.Forms.ToolStrip> de un control <xref:System.Windows.Forms.ToolStripPanel> a otro.  
  
## Pasos siguientes  
 En este tutorial, ha creado un formulario MDI principal con controles <xref:System.Windows.Forms.ToolStrip> y combinación de menús.  Puede utilizar la familia <xref:System.Windows.Forms.ToolStrip> de controles para muchos otros propósitos:  
  
-   Crear menús contextual para los controles con <xref:System.Windows.Forms.ContextMenuStrip>.  Para obtener más información, vea [Información general sobre ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
-   Formulario creado con un menú estándar rellenado automáticamente.  Para obtener más información, vea [Tutorial: Proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).  
  
-   Proporcionar a los controles <xref:System.Windows.Forms.ToolStrip> un aspecto profesional.  Para obtener más información, vea [Cómo: Establecer la representación de ToolStrip para una aplicación](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [Cómo: Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Cómo: Crear formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [Cómo: Insertar un elemento MenuStrip en un menú desplegable MDI](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)   
 [ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)