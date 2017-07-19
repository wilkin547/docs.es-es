---
title: "Informaci&#243;n general sobre el componente OpenFileDialog (formularios Windows Forms) | Microsoft Docs"
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
  - "OpenFileDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Abrir archivo (cuadro de diálogo), mostrar en Windows Forms"
  - "OpenFileDialog (componente), acerca de OpenFileDialog"
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre el componente OpenFileDialog (formularios Windows Forms)
El componente <xref:System.Windows.Forms.OpenFileDialog> de Windows Forms es un cuadro de diálogo preconfigurado.  Es el mismo cuadro de diálogo **Abrir archivo** que expone el sistema operativo de Windows.  Se hereda de la clase <xref:System.Windows.Forms.CommonDialog>.  
  
## Utilizar este componente  
 Utilice este componente dentro de la aplicación para Windows como una solución sencilla para seleccionar archivos, en lugar de configurar un cuadro de diálogo propio.  Al basarse en cuadros de diálogo estándar de Windows, creará aplicaciones cuya funcionalidad básica les resultará inmediatamente familiar a los usuarios.  Tenga en cuenta, no obstante, que cuando utilice el componente <xref:System.Windows.Forms.OpenFileDialog> deberá escribir su propia lógica de almacenamiento de archivos.  
  
 Utilice el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo en tiempo de ejecución.  Para permitir que los usuarios seleccionen múltiples archivos para abrirlos, utilice la propiedad <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>.  Además, puede utilizar la propiedad <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> para determinar si aparecerá una casilla de sólo lectura en el cuadro de diálogo.  La propiedad <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> indica si la casilla de sólo lectura está activada.  Por último, la propiedad <xref:System.Windows.Forms.FileDialog.Filter%2A> establece la cadena de filtro de nombres de archivo actual, que determina las opciones que aparecen en el cuadro "Tipo de archivos" del cuadro de diálogo.  
  
 Cuando se agrega a un formulario, el componente <xref:System.Windows.Forms.OpenFileDialog> aparece en la bandeja de la parte inferior del Diseñador de Windows Forms.  
  
## Vea también  
 <xref:System.Windows.Forms.OpenFileDialog>   
 [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)