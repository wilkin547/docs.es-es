---
title: "Informaci&#243;n general sobre el componente HelpProvider (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "HelpProvider"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadros de diálogo, Ayuda contextual"
  - "Ayuda F1, agregar a Windows Forms"
  - "Ayuda, agregar a aplicaciones para Windows"
  - "HelpProvider (componente) [Windows Forms], acerca del componente HelpProvider"
  - "Windows Forms, Ayuda contextual"
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Informaci&#243;n general sobre el componente HelpProvider (formularios Windows Forms)
El componente [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) de formularios Windows Forms se utiliza para asociar un archivo de Ayuda HTML Help 1.x \(ya sea un archivo .chm, generado con HTML Help Workshop o un archivo .htm\) a una aplicación para Windows.  Puede proporcionar ayuda de varias maneras:  
  
-   Proporcionar ayuda contextual para controles de formularios Windows Forms.  
  
-   Proporcionar ayuda contextual sobre un cuadro de diálogo en particular o sobre controles específicos de un cuadro de diálogo.  
  
-   Abrir un archivo de Ayuda en áreas específicas, como la página principal de una Tabla de contenido, el Índice o una función de búsqueda.  
  
## Utilizar el proveedor de ayuda  
 Al agregar un componente <xref:System.Windows.Forms.HelpProvider> a su Windows Form permite a los otros controles del formulario exponer las propiedades de ayuda del componente <xref:System.Windows.Forms.HelpProvider>.  Esto le permite proporcionar ayuda para los controles en su Windows Form.  Puede asociar un archivo de Ayuda al componente <xref:System.Windows.Forms.HelpProvider> por medio de la propiedad <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>.  Para especificar el tipo de ayuda que se desea proporcionar, llame al método <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> y proporcione un valor de la enumeración <xref:System.Windows.Forms.HelpNavigator> al control especificado.  Para proporcionar la palabra clave o tema de la ayuda, llame al método <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>.  
  
 Opcionalmente, puede utilizar el método <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> para asociar una cadena de Ayuda específica a otro control.  Cuando el usuario presione la tecla F1 mientras el control tiene el foco, la cadena asociada por medio de este método se mostrará en una ventana emergente.  
  
 Si no se ha establecido <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>, debe utilizar <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> para proporcionar el texto de la Ayuda.  Si estableció tanto <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> como la cadena de Ayuda, tendrá precedencia la Ayuda basada en <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>.  
  
> [!NOTE]
>  Podría encontrar problemas si utiliza la ruta acceso relativa al especificar la ruta de acceso al archivo de Ayuda en el método <xref:System.Windows.Forms.Help.ShowHelp%2A> o la propiedad<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> del control<xref:System.Windows.Forms.HelpProvider>.  Por tanto, asegúrese de utilizar la ruta absoluta de acceso al archivo para especificar el archivo de Ayuda.  
  
## Vea también  
 [Help Systems in Windows Forms Applications](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)