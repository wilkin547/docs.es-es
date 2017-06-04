---
title: "Informaci&#243;n general sobre el componente SaveFileDialog (formularios Windows Forms) | Microsoft Docs"
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
  - "SaveFileDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Guardar archivo (cuadro de diálogo), mostrar"
  - "SaveFileDialog (componente), acerca de SaveFileDialog"
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Informaci&#243;n general sobre el componente SaveFileDialog (formularios Windows Forms)
El componente <xref:System.Windows.Forms.SaveFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado.  Es el mismo cuadro de diálogo **Guardar archivo** que utiliza Windows.  Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.  
  
## Trabajar con el componente SaveFileDialog  
 Utilícelo como una solución sencilla para permitir que los usuarios guarden archivos, en lugar de configurar un cuadro de diálogo propio.  Si se apoya en cuadros de diálogo estándar de Windows, la funcionalidad básica de las aplicaciones que cree resultará inmediatamente familiar para los usuarios.  Tenga en cuenta, no obstante, que cuando utilice el componente <xref:System.Windows.Forms.SaveFileDialog> deberá escribir su propia lógica de almacenamiento de archivos.  
  
 Puede utilizar el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución.  Para abrir un archivo en modo de lectura y escritura, puede utilizar el método <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>.  
  
 Cuando se agrega a un formulario, el componente <xref:System.Windows.Forms.SaveFileDialog> aparece en la bandeja de la parte inferior del Diseñador de Windows Forms.  
  
## Vea también  
 <xref:System.Windows.Forms.SaveFileDialog>   
 [SaveFileDialog](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)