---
title: "Informaci&#243;n general del componente FolderBrowserDialog (formularios Windows Forms) | Microsoft Docs"
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
  - "FolderBrowserDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "directorios [Windows Forms], habilitar examinar en aplicaciones"
  - "FolderBrowserDialog (componente) [Windows Forms], acerca de FolderBrowserDialog"
  - "carpetas [Windows Forms], habilitar examinar en aplicaciones"
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Informaci&#243;n general del componente FolderBrowserDialog (formularios Windows Forms)
El componente <xref:System.Windows.Forms.FolderBrowserDialog> de formularios Windows Forms es un cuadro de diálogo modal que se utiliza para examinar y seleccionar carpetas.  También se pueden crear carpetas nuevas desde el componente <xref:System.Windows.Forms.FolderBrowserDialog>.  
  
> [!NOTE]
>  Para seleccionar archivos, en lugar de carpetas, utilice el componente [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md).  
  
 El componente <xref:System.Windows.Forms.FolderBrowserDialog> se muestra en tiempo de ejecución mediante el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  Establezca la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> para determinar la carpeta de nivel superior y las subcarpetas que aparecerán en la vista árbol del cuadro de diálogo.  Una vez mostrado el cuadro de diálogo, puede utilizar la propiedad <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> para obtener la ruta de acceso de la carpeta seleccionada.  
  
 Cuando se agrega a un formulario, el componente <xref:System.Windows.Forms.FolderBrowserDialog> aparece en la bandeja de la parte inferior del Diseñador de Windows Forms.  
  
## Vea también  
 <xref:System.Windows.Forms.FolderBrowserDialog>   
 [Cómo: Elegir carpetas con el componente FolderBrowserDialog de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)   
 [FolderBrowserDialog](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)