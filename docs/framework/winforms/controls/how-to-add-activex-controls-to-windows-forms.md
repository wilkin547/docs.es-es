---
title: "C&#243;mo: Agregar controles ActiveX a formularios Windows Forms | Microsoft Docs"
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
  - "controles ActiveX [Windows Forms], agregar"
  - "formularios, agregar controles ActiveX"
  - "controles de Windows Forms, controles ActiveX"
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Agregar controles ActiveX a formularios Windows Forms
Aunque el Diseñador de Windows Forms está optimizado para hospedar controles de formularios Windows Forms, es posible utilizar también controles ActiveX en formularios Windows Forms.  
  
> [!CAUTION]
>  Cuando se agregan controles ActiveX a formularios Windows Forms, existen limitaciones de rendimiento.  
  
 Antes de agregar controles ActiveX a un formulario, debe agregarlos al Cuadro de herramientas.  Para obtener más información, vea [Componentes COM, cuadro de herramientas Personalizar \(cuadro de diálogo\)](http://msdn.microsoft.com/es-es/171333f3-f207-4e02-bbdc-17862556212c).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar su configuración, haga clic en **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar un control ActiveX a un Windows Form  
  
-   Haga doble clic en el control en el Cuadro de herramientas.  
  
     [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] agregará al proyecto todas las referencias al control.  Para obtener más información sobre los aspectos que se deben tener en cuenta cuando se utilizan controles ActiveX en Windows Forms, vea [Consideraciones para hospedar un control ActiveX en un Windows Form](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  El Importador de controles ActiveX de formularios Windows Forms \(AxImp.exe\) crea argumentos de evento de un tipo distinto del esperado cuando importa bibliotecas de vínculos dinámicos de ActiveX.  Los argumentos creados por AxImp.exe son similares a: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, cuando se espera `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`.  Tenga en cuenta que dicha irregularidad no impide que el código funcione con normalidad.  Para obtener información detallada, vea [Importador de controles ActiveX de formularios Windows Forms \(Aximp.exe\)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## Vea también  
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](http://msdn.microsoft.com/es-es/021f2a1b-8247-4348-a5ad-e1d9ab23004b)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)   
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)