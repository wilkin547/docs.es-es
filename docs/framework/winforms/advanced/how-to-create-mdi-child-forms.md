---
title: "C&#243;mo: Crear formularios MDI secundarios | Microsoft Docs"
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
  - "formularios secundarios"
  - "MDI, crear formularios"
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# C&#243;mo: Crear formularios MDI secundarios
Los formularios secundarios MDI son un elemento esencial de las [Aplicaciones de interfaz de múltiples documentos \(MDI\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), ya que estos formularios son el centro de la interacción del usuario.  
  
 En el siguiente procedimiento, va a crear formulario MDI secundario que muestra un control <xref:System.Windows.Forms.RichTextBox>, similar a la mayoría de las aplicaciones de procesamiento de texto.  Sustituir el control <xref:System.Windows.Forms> por otros controles, como el control <xref:System.Windows.Forms.DataGridView>, o por una mezcla de controles permite crear ventanas secundarias MDI \(y, por extensión, aplicaciones MDI\) con diversas posibilidades.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear formularios secundarios MDI  
  
1.  Cree un nuevo proyecto de Windows Forms.  En **la ventana Propiedades** del formulario, establezca la propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true` y la propiedad `WindowsState` en `Maximized`.  
  
     Esto hace que el formulario se designe como contenedor MDI de las ventanas secundarias.  
  
2.  Desde el `Toolbox`, arrastre un control <xref:System.Windows.Forms.MenuStrip> al formulario.  Establezca la propiedad `Text` en **Archivo**.  
  
3.  Haga clic en el botón de puntos suspensivos \(...\) junto a la propiedad **Elementos** y haga clic en **Agregar** para agregar dos elementos de menú de barra de herramientas secundarios.  Establezca la propiedad `Text` de estos elementos en **Nuevo** y **Ventana**.  
  
4.  En el **Explorador de soluciones**, haga clic con el botón secundario en el proyecto, apunte a **Agregar** y, después, seleccione **Agregar nuevo elemento**.  
  
5.  En el cuadro de diálogo **Agregar nuevo elemento**, seleccione **Windows Form** \(en [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o en [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) o **Aplicación de Windows Forms \(. NET\)** \(en [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) en el panel **Plantillas**.  En el cuadro **Nombre**, asigne al formulario el nombre Form2.  Haga clic en el botón **Abrir** agregar el formulario al proyecto.  
  
    > [!NOTE]
    >  El formulario secundario MDI creado en este paso es un Windows Form estándar.  Como tal, tiene una propiedad <xref:System.Windows.Forms.Form.Opacity%2A>, que le permite controlar la transparencia del formulario.  Sin embargo, la propiedad <xref:System.Windows.Forms.Form.Opacity%2A> se diseñó para ventanas de nivel superior.  No la use con formularios secundarios MDI porque se pueden producir problemas de dibujo.  
  
     Este formulario será la plantilla para los formularios secundarios MDI.  
  
     Se abre el **Diseñador de Windows Forms** y muestra Form2.  
  
6.  Desde el **Cuadro de herramientas**, arrastre un control **RichTextBox** al formulario.  
  
7.  En la ventana **Propiedades**, establezca la propiedad `Anchor` en **Superior, Izquierda** y la propiedad `Dock` en **Rellenar**.  
  
     Esto hace que el control <xref:System.Windows.Forms.RichTextBox> rellene completamente el área del formulario MDI secundario, incluso cuando se cambia el tamaño del formulario.  
  
8.  Haga doble clic en el elemento de menú **Nuevo** para crear un controlador de eventos <xref:System.Windows.Forms.Control.Click> para él.  
  
9. Inserte código similar al siguiente para crear un nuevo formulario MDI secundario cuando el usuario haga clic en el elemento de menú **Nuevo**.  
  
    > [!NOTE]
    >  En el ejemplo siguiente, el controlador de eventos controla el evento <xref:System.Windows.Forms.Control.Click> para `MenuItem2`.  Tenga en cuenta que, según las particularidades de la arquitectura de su aplicación, puede que el elemento de menú **Nuevo** no sea `MenuItem2`.  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     En [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], agregue la siguiente directiva `#include` al principio de Form1.h:  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. En la lista desplegable situada en la parte superior de la ventana **Propiedades**, seleccione la franja de menú que corresponde a la franja de menú **Archivo** y establezca la propiedad <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> en el <xref:System.Windows.Forms.ToolStripMenuItem> de Ventana.  
  
     Esto permitirá al menú **Ventana** mantener una lista de las ventanas MDI secundarias abiertas con una marca de verificación junto a la ventana secundaria activa.  
  
11. Presione F5 para ejecutar la aplicación.  Seleccione **Nuevo** en el menú **Archivo** para crear nuevos formularios MDI secundarios de los que se realiza un seguimiento en el elemento de menú **Ventana**.  
  
    > [!NOTE]
    >  Cuando un formulario MDI secundario tiene un componente <xref:System.Windows.Forms.MainMenu> \(por lo general, con una estructura de menús con elementos de menú\) y se abre dentro de un formulario MDI primario que tiene un componente <xref:System.Windows.Forms.MainMenu> \(por lo general, con una estructura de menús con elementos de menú\), los elementos de menú se combinan automáticamente si ha establecido la propiedad <xref:System.Windows.Forms.MenuItem.MergeType%2A> \(y, opcionalmente, la propiedad <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>\).  Establezca la propiedad <xref:System.Windows.Forms.MenuItem.MergeType%2A> de ambos componentes <xref:System.Windows.Forms.MainMenu> y todos los elementos de menú del formulario secundario en <xref:System.Windows.Forms.MenuMerge>.  Además, establezca la propiedad <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> para que los elementos de ambos menús aparezcan en el orden deseado.  Tenga en cuenta también que, cuando se cierra un formulario MDI primario, cada uno de los formularios MDI secundarios genera un evento <xref:System.Windows.Forms.Form.Closing> antes de que se produzca el evento <xref:System.Windows.Forms.Form.Closing> para el formulario MDI primario.  Cancelar el evento <xref:System.Windows.Forms.Form.Closing> de un elemento MDI secundario no impedirá que se produzca el evento <xref:System.Windows.Forms.Form.Closing> del elemento MDI primario; sin embargo, el argumento <xref:System.ComponentModel.CancelEventArgs> del evento <xref:System.Windows.Forms.Form.Closing> del elemento MDI primario ahora se establecerá en `true`.  Puede forzar el cierre del formularios MDI primario y de todos los formularios MDI secundarios estableciendo el argumento <xref:System.ComponentModel.CancelEventArgs> en `false`.  
  
## Vea también  
 [Aplicaciones de interfaz de múltiples documentos \(MDI\)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)   
 [Cómo: Crear formularios principales MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [Cómo: Determinar el formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)   
 [Cómo: Enviar datos al formulario secundario MDI activo](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)   
 [Cómo: Organizar formularios MDI secundarios](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)