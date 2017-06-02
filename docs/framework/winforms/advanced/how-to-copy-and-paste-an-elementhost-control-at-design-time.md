---
title: "C&#243;mo: Copiar y pegar un control ElementHost en tiempo de dise&#241;o | Microsoft Docs"
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
  - "ElementHost (control), copiar y pegar en tiempo de diseño"
  - "interoperabilidad [WPF]"
  - "Windows Forms, copiar y pegar contenido"
  - "WPF (control de usuario), hospedar en Windows Forms"
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Copiar y pegar un control ElementHost en tiempo de dise&#241;o
En este procedimiento se muestra cómo copiar un control de Windows Presentation Foundation \(WPF\) en un Windows Form.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para copiar y pegar un control ElementHost en tiempo de diseño  
  
1.  Agregue un nuevo control de WPF <xref:System.Windows.Controls.UserControl> a su proyecto de formularios Windows Forms.  Use el nombre predeterminado para el tipo de control, `UserControl1.xaml`.  Para obtener más información, consulte [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  En la ventana **Propiedades**, establezca el valor de las propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> de `UserControl1` en `200`.  
  
3.  Establezca el valor de la propiedad <xref:System.Windows.Controls.Control.Background%2A> en `Azul`.  
  
4.  Compile el proyecto.  
  
5.  Abra `Form1` en el Diseñador de Windows Forms.  
  
6.  En el **Cuadro de herramientas**, arrastre una instancia de `UserControl1` al formulario.  
  
     Una instancia de `UserControl1` se hospeda en un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> denominado `elementHost1`.  
  
7.  Con `elementHost1` seleccionado, presione CTRL\+C para copiarlo en el Portapapeles.  
  
8.  Presione CTRL\+V para pegar el control copiado en el formulario.  
  
     Se crea un nuevo control <xref:System.Windows.Forms.Integration.ElementHost> denominado `elementHost2` en el formulario.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Tutorial: Copiar y pegar un control ElementHost en formularios Windows Forms independientes](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)   
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)   
 [Utilizar controles WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)