---
title: "C&#243;mo: Aplicar el modelo PropertyNameChanged | Microsoft Docs"
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
  - "controles personalizados [Windows Forms], cambios en las propiedades (utilizando el código)"
  - "enlace de datos, controles personalizados"
  - "PropertyNameChanged (modelo), aplicar"
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Aplicar el modelo PropertyNameChanged
En el ejemplo de código siguiente se muestra cómo aplicar el modelo *nombreDePropiedad*Changed a un control personalizado.  Aplique este modelo cuando implemente los controles personalizados utilizados con el motor de enlace de datos de Windows Forms.  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## Compilar el código  
 Para compilar el ejemplo de código anterior:  
  
-   Pegue el código en un archivo de código vacío.  Debe utilizar el control personalizado en un Windows Form que contenga un método `Main`.  
  
## Vea también  
 [Cómo: Implementar la interfaz INotifyPropertyChanged](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)   
 [Notificación de cambios en el enlace de datos de Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)