---
title: "C&#243;mo: Seleccionar un elemento del control ListView de formularios Windows Forms | Microsoft Docs"
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
  - "vistas de lista, seleccionar elementos"
  - "listas, seleccionar elementos"
  - "ListView (control) [Windows Forms], seleccionar elementos"
  - "selección, en vistas de lista"
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Seleccionar un elemento del control ListView de formularios Windows Forms
En este ejemplo se muestra cómo seleccionar mediante programación un elemento de un control <xref:System.Windows.Forms.ListView> de los formularios Windows Forms.  Al seleccionar un elemento mediante programación, no se cambia automáticamente el foco al control <xref:System.Windows.Forms.ListView>.  Por esta razón, al seleccionar un elemento, normalmente querrá también establecer este elemento como el elemento que tiene el foco.  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.ListView> denominado `listView1` que contenga al menos un elemento.  
  
-   Referencias a los espacios de nombres <xref:System?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=fullName>