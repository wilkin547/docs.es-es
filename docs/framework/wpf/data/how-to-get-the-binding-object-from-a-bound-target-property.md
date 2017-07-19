---
title: "C&#243;mo: Obtener el objeto de enlace a partir de una propiedad de destino enlazada | Microsoft Docs"
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
  - "enlace de datos, obtener objetos de enlace a partir de propiedades de destino enlazadas"
  - "propiedades, obtener objetos de enlace a partir de"
ms.assetid: 87974c5f-136b-4de7-b07d-9285b62ab123
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Obtener el objeto de enlace a partir de una propiedad de destino enlazada
En este ejemplo se muestra cómo obtener el objeto de enlace de una propiedad de destino enlazada a datos.  
  
## Ejemplo  
 Puede hacer lo siguiente para obtener el objeto <xref:System.Windows.Data.Binding>:  
  
 [!code-csharp[BindValidation#GetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml.cs#getbinding)]  
  
> [!NOTE]
>  Debe especificar la [propiedad de dependencia](GTMT) del enlace que desea obtener, porque es posible que el enlace de datos se utilice en más de una propiedad del objeto de destino.  
  
 Como alternativa, puede obtener <xref:System.Windows.Data.BindingExpression> y, a continuación, obtener el valor de la propiedad <xref:System.Windows.Data.BindingExpression.ParentBinding%2A>.  
  
 Para obtener el ejemplo completo, vea [Binding Validation Sample](http://go.microsoft.com/fwlink/?LinkID=159972).  
  
> [!NOTE]
>  Si el enlace es un objeto <xref:System.Windows.Data.MultiBinding>, utilice <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetMultiBinding%2A>.  Si es una propiedad <xref:System.Windows.Data.PriorityBinding>, utilice <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetPriorityBinding%2A>.  Si no está seguro de si la propiedad de destino se ha enlazado mediante <xref:System.Windows.Data.Binding>, <xref:System.Windows.Data.MultiBinding> o <xref:System.Windows.Data.PriorityBinding>, puede utilizar <xref:System.Windows.Data.BindingOperations>.<xref:System.Windows.Data.BindingOperations.GetBindingBase%2A>.  
  
## Vea también  
 [Crear un enlace mediante código](../../../../docs/framework/wpf/data/how-to-create-a-binding-in-code.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)