---
title: "C&#243;mo: Implementar la interfaz INotifyPropertyChanged | Microsoft Docs"
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
  - "INotifyPropertyChanged (interfaz), implementar"
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Implementar la interfaz INotifyPropertyChanged
En el ejemplo de código siguiente, se muestra cómo implementar la interfaz <xref:System.ComponentModel.INotifyPropertyChanged>.  Implemente esta interfaz en los objetos comerciales utilizados en el enlace de datos de los formularios Windows Forms.  Una vez implementada, la interfaz comunica a un control enlazado los cambios de propiedad de un objeto comercial.  
  
## Ejemplo  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## Vea también  
 [Cómo: Aplicar el modelo PropertyNameChanged](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)   
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Cómo: Provocar notificaciones de cambios mediante BindingSource y la interfaz INotifyPropertyChanged](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)   
 [Notificación de cambios en el enlace de datos de Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)