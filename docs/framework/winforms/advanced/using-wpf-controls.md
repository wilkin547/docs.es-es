---
title: "Utilizar controles WPF | Microsoft Docs"
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
  - "interoperabilidad [WPF]"
  - "Diseñador de Windows Forms, interoperabilidad con WPF"
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Utilizar controles WPF
Puede utilizar los controles de Windows Presentation Foundation \(WPF\) en sus aplicaciones basadas en formularios Windows Forms.  Aunque se trata de dos tecnologías de presentación diferentes, operan perfectamente entre sí.  
  
 El Diseñador de Windows Forms proporciona un entorno de diseño visual para hospedar los controles de Windows Presentation Foundation.  Los controles de WPF se hospedan en un control de formularios Windows Forms especial denominado <xref:System.Windows.Forms.Integration.ElementHost>.  Este control permite que el control de WPF participe en el diseño del formulario y reciba mensajes del teclado y del mouse.  En tiempo de diseño, puede organizar el control <xref:System.Windows.Forms.Integration.ElementHost> como cualquier otro control de formularios Windows Forms.  
  
 Puede utilizar también los controles de formularios Windows Forms en sus aplicaciones de WPF.  Para obtener más información, consulte [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26).  
  
## En esta sección  
 [Cómo: Copiar y pegar un control ElementHost en tiempo de diseño](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 Muestra cómo copiar un control de Windows Presentation Foundation en un Windows Form.  
  
 [Tutorial: Organizar el contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 Muestra cómo utilizar las características de diseño de formularios Windows Forms, como delimitaciones y líneas de ajuste, para organizar los controles de Windows Presentation Foundation.  
  
 [Tutorial: Cambiar propiedades de un elemento WPF hospedado en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 Muestra el flujo de trabajo entre el Diseñador de Windows Forms y [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] para cambiar las propiedades de controles de WPF.  
  
 [Tutorial: Crear nuevo contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 Muestra cómo crear un control de Windows Presentation Foundation para utilizarlo en las aplicaciones de formularios Windows Forms.  
  
 [Tutorial: Copiar y pegar un control ElementHost en formularios Windows Forms independientes](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 Muestra cómo copiar un control de Windows Presentation Foundation de un Windows Form a otro.  
  
 [Tutorial: Asignar el contenido de WPF en Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 Muestra cómo seleccionar los tipos de controles de Windows Presentation Foundation que desea mostrar en su formulario.  
  
 [Tutorial: Aplicar estilos al contenido de WPF](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 Muestra el flujo de trabajo entre el Diseñador de Windows Forms y [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] para aplicar estilos a los controles de Windows Presentation Foundation.  
  
## Referencia  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 Describe una clase que puede utilizar para hospedar controles de Windows Presentation Foundation en sus aplicaciones de formularios Windows Forms.  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 Describe una clase que puede utilizar para hospedar controles de formularios Windows Forms en sus aplicaciones de Windows Presentation Foundation.  
  
## Secciones relacionadas  
 [Migración e interoperabilidad](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 Describe cómo interactúan las tecnologías de Windows Presentation Foundation y formularios Windows Forms.  
  
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)  
 Describe cómo diseñar controles de Windows Presentation Foundation en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].