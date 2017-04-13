---
title: "C&#243;mo: Implementar la interfaz ITypedList | Microsoft Docs"
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
  - "BindingList(Of T) (clase)"
  - "enlace de datos, implementar"
  - "IBindingList (interfaz)"
  - "ITypedList (interfaz)"
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Implementar la interfaz ITypedList
Implemente la interfaz <xref:System.ComponentModel.ITypedList> para habilitar la detección del esquema para obtener una lista enlazable.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo implementar la interfaz <xref:System.ComponentModel.ITypedList>.  Un tipo genérico llamado `SortableBindingList` deriva de la clase <xref:System.ComponentModel.BindingList%601> e implementa la interfaz <xref:System.ComponentModel.ITypedList>.  Una clase simple llamada `Customer` proporciona los datos, que se enlazan al encabezado de un control <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System.Drawing y System.Windows.Forms.  
  
## Vea también  
 <xref:System.ComponentModel.ITypedList>   
 <xref:System.ComponentModel.BindingList%601>   
 <xref:System.ComponentModel.IBindingList>   
 [Enlace de datos y formularios Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)