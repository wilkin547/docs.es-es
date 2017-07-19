---
title: "C&#243;mo: Crear una interfaz de usuario de varios paneles con formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "interfaz de usuario de varios paneles"
  - "SplitContainer (control) [Windows Forms], mediante el diseñador"
  - "interfaz de usuario, de varios paneles"
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Crear una interfaz de usuario de varios paneles con formularios Windows Forms mediante el Dise&#241;ador
El procedimiento siguiente permite crear una interfaz de usuario de varios paneles parecida a la utilizada en Microsoft Outlook, con una lista de **Carpetas**, un panel de **Mensajes** y un panel de **Vista previa**.  Esta organización se logra principalmente mediante el acoplamiento de los controles con el formulario.  
  
 Al acoplar un control se determina a cuál de los bordes del contenedor principal deberá fijarse.  Por consiguiente, si establece la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle>, el borde derecho del control se acoplará al borde derecho de su control primario.  Además, el tamaño del borde acoplado del control se ajusta al tamaño del control contenedor.  Para obtener más información sobre cómo funciona la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A>, vea [Cómo: Acoplar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).  
  
 Este procedimiento se centra en organizar el contenedor <xref:System.Windows.Forms.SplitContainer> y los demás controles del formulario, no se trata de agregar funcionalidades para obtener una aplicación que imite a Microsoft Outlook.  
  
 Para crear esta interfaz de usuario, se colocan todos los controles dentro de un control <xref:System.Windows.Forms.SplitContainer> que, a su vez, contiene un control <xref:System.Windows.Forms.TreeView> en el panel izquierdo.  El panel derecho del control <xref:System.Windows.Forms.SplitContainer> contiene un segundo control <xref:System.Windows.Forms.SplitContainer>, que a su vez tiene un control <xref:System.Windows.Forms.ListView> por encima de un control <xref:System.Windows.Forms.RichTextBox>.  Estos controles <xref:System.Windows.Forms.SplitContainer> permiten realizar el ajuste del tamaño de los demás controles del formulario de manera independiente.  Puede adaptar las técnicas de este procedimiento para crear interfaces de usuario personalizadas propias.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para crear una interfaz de usuario de estilo Outlook en tiempo de diseño  
  
1.  Cree un proyecto nuevo de aplicación para Windows.  Para obtener información detallada, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Arrastre un control <xref:System.Windows.Forms.SplitContainer> desde el **Cuadro de herramientas** hasta el formulario.  En la ventana **Propiedades**, establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle>.  
  
3.  Arrastre un control <xref:System.Windows.Forms.TreeView> del **Cuadro de herramientas** hasta el panel izquierdo del control <xref:System.Windows.Forms.SplitContainer>.  En la ventana **Propiedades**, establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle> haciendo clic en el panel izquierdo del editor de valor que aparece cuando se hace clic en la flecha hacia abajo.  
  
4.  Arrastre otro control <xref:System.Windows.Forms.SplitContainer> del **Cuadro de herramientas** y colóquelo en el panel derecho del control <xref:System.Windows.Forms.SplitContainer> que agregó al formulario.  En la ventana **Propiedades**, establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> en <xref:System.Windows.Forms.DockStyle>, y la propiedad <xref:System.Windows.Forms.SplitContainer.Orientation%2A> en <xref:System.Windows.Forms.Orientation>.  
  
5.  Arrastre un control <xref:System.Windows.Forms.ListView> del **Cuadro de herramientas** hasta el panel superior del segundo control <xref:System.Windows.Forms.SplitContainer> que agregó al formulario.  Establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> del control <xref:System.Windows.Forms.ListView> en <xref:System.Windows.Forms.DockStyle>.  
  
6.  Arrastre un control <xref:System.Windows.Forms.RichTextBox> del **Cuadro de herramientas** hasta el panel inferior del segundo control <xref:System.Windows.Forms.SplitContainer>.  Establezca la propiedad <xref:System.Windows.Forms.SplitContainer.Dock%2A> del control <xref:System.Windows.Forms.RichTextBox> en <xref:System.Windows.Forms.DockStyle>.  
  
     En este punto, si presiona F5 para ejecutar la aplicación, el formulario muestra una interfaz de usuario de tres partes, similar a la de Microsoft Outlook.  
  
    > [!NOTE]
    >  Al colocar el puntero del mouse sobre cualquiera de los divisores de los controles <xref:System.Windows.Forms.SplitContainer>, puede cambiar el tamaño de las dimensiones internas.  
  
     Llegado este punto del desarrollo de la aplicación, ha diseñado una interfaz de usuario compleja.  El paso siguiente consiste en continuar con la programación de la propia aplicación, quizás conectar el control <xref:System.Windows.Forms.TreeView> y los controles <xref:System.Windows.Forms.ListView> a algún tipo de origen de datos.  Para obtener más información sobre el modo de conectar controles con datos, vea [Enlace de datos y formularios Windows Forms](../../../../docs/framework/winforms/data-binding-and-windows-forms.md).  
  
## Vea también  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer \(Control\)](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)