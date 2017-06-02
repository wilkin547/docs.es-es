---
title: "C&#243;mo: Mostrar ayuda emergente | Microsoft Docs"
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
  - "Ayuda F1, en cuadros de diálogo"
  - "formularios, mostrar la Ayuda"
  - "Ayuda, agregar a cuadros de diálogo"
  - "Ayuda, Ayuda emergente"
  - "HelpProvider (componente) [Windows Forms]"
  - "cuadros de diálogo modales, Ayuda emergente"
  - "Ayuda emergente"
  - "Windows Forms, mostrar la Ayuda"
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Mostrar ayuda emergente
Una forma de mostrar la Ayuda en Windows Forms es mediante el botón **Ayuda**, situado en el lado derecho de la barra de título y accesible mediante la propiedad <xref:System.Windows.Forms.Form.HelpButton%2A>.  Este tipo de visualización de la Ayuda está indicado para cuadros de diálogo.  Los cuadros de diálogo que se muestran de forma modal \(con el método <xref:System.Windows.Forms.Form.ShowDialog%2A>\) tienen problemas para abrir los sistemas de Ayuda externos porque los cuadros de diálogo modales deben cerrarse antes de poder pasar el foco a otra ventana.  Además, para usar el botón **Ayuda** es necesario que no se muestre ningún botón **Minimizar** o **Maximizar** en la barra de título.  Esta es una convención estándar para cuadros de diálogo, mientras que los formularios normalmente tienen botones **Minimizar** y **Maximizar**.  
  
 Tenga en cuenta que también puede usar el componente <xref:System.Windows.Forms.HelpProvider> para vincular controles a archivos en un sistema de Ayuda, aunque haya implementado ayuda emergente.  Para obtener más información, consulte [Proporcionar ayuda en una aplicación para Windows](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para mostrar Ayuda emergente  
  
1.  Arrastre un componente [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) desde el cuadro de herramientas al formulario.  
  
     Se colocará en la bandeja, en la parte inferior del Diseñador de Windows Forms.  
  
2.  En la ventana de propiedades, establezca la propiedad <xref:System.Windows.Forms.Form.HelpButton%2A> en `true`.  Se mostrará un botón con un signo de interrogación en el lado derecho de la barra de título del formulario.  
  
3.  Para que el <xref:System.Windows.Forms.Form.HelpButton%2A> se muestre, las propiedades <xref:System.Windows.Forms.Form.MinimizeBox%2A> y <xref:System.Windows.Forms.Form.MaximizeBox%2A> del formulario deben establecerse en `false`, la propiedad <xref:System.Windows.Forms.Form.ControlBox%2A> debe establecerse en `true` y la propiedad <xref:System.Windows.Forms.Form.FormBorderStyle%2A> debe establecerse en uno de los siguientes valores: <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle>, <xref:System.Windows.Forms.FormBorderStyle> o <xref:System.Windows.Forms.FormBorderStyle>.  
  
4.  Seleccione el control para el que quiere mostrar la Ayuda en el formulario y establezca la cadena de Ayuda en la ventana Propiedades.  Esta es la cadena de texto que se mostrará en una ventana similar a una [información sobre herramientas](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).  
  
5.  Presione **F5**.  
  
6.  Presione el botón **Ayuda** en la barra de título y haga clic en el control en el que se establece la cadena de Ayuda.  
  
## Vea también  
 [Controlar la ayuda mediante información sobre herramientas](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)   
 [Integrar la Ayuda de usuario en formularios Windows Forms](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)