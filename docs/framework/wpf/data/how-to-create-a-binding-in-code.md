---
title: "C&#243;mo: Crear un enlace en c&#243;digo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "enlazar datos, crear"
  - "enlace de datos, crear"
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# C&#243;mo: Crear un enlace en c&#243;digo
En este ejemplo se muestra cómo crear y establecer un objeto <xref:System.Windows.Data.Binding> en código.  
  
## Ejemplo  
 Las clases <xref:System.Windows.FrameworkElement> y <xref:System.Windows.FrameworkContentElement> exponen un método `SetBinding`.  Si enlaza un elemento que hereda de cualquiera de estas clases, puede llamar al método <xref:System.Windows.FrameworkElement.SetBinding%2A> directamente.  
  
 En el ejemplo siguiente se crea una clase denominada, `MyData`, que contiene una propiedad denominada `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 En el ejemplo siguiente se muestra cómo crear un objeto de enlace para establecer el origen del enlace.  En el ejemplo se utiliza <xref:System.Windows.FrameworkElement.SetBinding%2A> para enlazar la propiedad <xref:System.Windows.Controls.TextBlock.Text%2A> de `myText`, que es un control <xref:System.Windows.Controls.TextBlock>, a `MyDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Para obtener el ejemplo de código completo, consulte [Code\-only Binding Sample](http://msdn.microsoft.com/es-es/764aaf0b-2216-4941-9548-9c98da18d1a6).  
  
 En lugar de llamar a <xref:System.Windows.FrameworkElement.SetBinding%2A>, puede utilizar el método estático <xref:System.Windows.Data.BindingOperations.SetBinding%2A> de la clase <xref:System.Windows.Data.BindingOperations>.  En el ejemplo siguiente, se llama a <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=fullName> en lugar de a <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=fullName> para enlazar `myText` a `myDataProperty`.  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)