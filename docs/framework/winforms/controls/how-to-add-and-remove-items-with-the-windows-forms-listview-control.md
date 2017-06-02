---
title: "C&#243;mo: Agregar y quitar elementos con el control ListView de Windows Forms | Microsoft Docs"
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
  - "vistas de lista, agregar elementos de lista"
  - "ListView (control) [Windows Forms], agregar elementos de lista"
  - "ListView (control) [Windows Forms], llenar"
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Agregar y quitar elementos con el control ListView de Windows Forms
El proceso de agregar un elemento a un control <xref:System.Windows.Forms.ListView> de formularios Windows Forms consiste básicamente en especificar el elemento y asignarle propiedades.  Puede agregar o quitar elementos de la lista en cualquier momento.  
  
### Para agregar elementos mediante programación  
  
1.  Utilice el método <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> de la propiedad <xref:System.Windows.Forms.ListView.Items%2A>.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### Para quitar elementos mediante programación  
  
1.  Utilice el método <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> de la propiedad <xref:System.Windows.Forms.ListView.Items%2A>.  El método <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> quita un solo elemento; el método <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> quita todos los elementos de la lista.  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## Vea también  
 <xref:System.Windows.Forms.ListView>   
 [ListView \(Control\)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)