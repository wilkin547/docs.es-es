---
title: "C&#243;mo: Implementar un adorno | Microsoft Docs"
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
  - "adornos, implementar"
ms.assetid: 56ae32b6-0599-455c-b52f-2ff97e6f1ec2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Implementar un adorno
En este ejemplo se muestra una implementación del adorno mínima.  
  
## Notas para los implementadores  
 Es importante tener en cuenta que los adornos no incluyen ningún comportamiento de representación inherente; asegurarse de que un adorno se representa es responsabilidad del implementador del adorno.  Una manera común de implementar el comportamiento de representación es invalidar el método <xref:System.Windows.UIElement.OnRender%2A> y utilizar uno o más objetos <xref:System.Windows.Media.DrawingContext> para representar los elementos visuales del adorno, según sea necesario \(como se muestra en este ejemplo\).  
  
## Ejemplo  
  
### Descripción  
 Un adorno personalizado se crea implementando una clase que hereda de la clase <xref:System.Windows.Documents.Adorner> abstracta.  El adorno del ejemplo simplemente adorna las esquinas de un elemento <xref:System.Windows.UIElement> con círculos invalidando el método <xref:System.Windows.UIElement.OnRender%2A>.  
  
### Código  
 [!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
 [!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]  
  
## Vea también  
 [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md)