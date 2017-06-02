---
title: "C&#243;mo: Agregar datos personalizados a datos de entrada manuscrita | Microsoft Docs"
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
  - "datos de entradas manuscritas, agregar datos personalizados"
  - "InkCanvas, mostrar"
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Agregar datos personalizados a datos de entrada manuscrita
Puede agregar datos personalizados a la entrada de lápiz, que se guardarán cuando la entrada de lápiz se guarde como Formato serializado de tinta \(ISF\).  Puede guardar los datos personalizados en <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection> o <xref:System.Windows.Ink.Stroke>.  La posibilidad de elegir entre tres objetos para guardar los datos personalizados le permite decidir cuál es el mejor lugar donde guardarlos.  Las tres clases usan métodos similares para almacenar y tener acceso a los datos personalizados.  
  
 Solo los tipos siguientes se pueden guardar como datos personalizados:  
  
-   <xref:System.Boolean>  
  
-   <xref:System.Boolean>\[\]  
  
-   <xref:System.Byte>  
  
-   <xref:System.Byte>\[\]  
  
-   <xref:System.Char>  
  
-   <xref:System.Char>\[\]  
  
-   <xref:System.DateTime>  
  
-   <xref:System.DateTime>\[\]  
  
-   <xref:System.Decimal>  
  
-   <xref:System.Decimal>\[\]  
  
-   <xref:System.Double>  
  
-   <xref:System.Double>\[\]  
  
-   <xref:System.Int16>  
  
-   <xref:System.Int16>\[\]  
  
-   <xref:System.Int32>  
  
-   <xref:System.Int32>\[\]  
  
-   <xref:System.Int64>  
  
-   <xref:System.Int64>\[\]  
  
-   <xref:System.Single>  
  
-   <xref:System.Single>\[\]  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <xref:System.UInt16>\[\]  
  
-   <xref:System.UInt32>  
  
-   <xref:System.UInt32>\[\]  
  
-   <xref:System.UInt64>  
  
-   <xref:System.UInt64>\[\]  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo agregar y recuperar datos personalizados de <xref:System.Windows.Ink.StrokeCollection>.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 En el ejemplo siguiente se crea una aplicación que muestra un objeto <xref:System.Windows.Controls.InkCanvas> y dos botones.  El botón, `switchAuthor`, permite que dos autores usen dos lápices diferentes.  El botón `changePenColors` cambia el color de cada trazo en <xref:System.Windows.Controls.InkCanvas> según el autor.  La aplicación define dos objetos <xref:System.Windows.Ink.DrawingAttributes> y agrega a cada uno una propiedad personalizada que indica qué autor dibujó el <xref:System.Windows.Ink.Stroke>.  Cuando el usuario hace clic en `changePenColors`, la aplicación cambia la apariencia del trazo según el valor de la propiedad personalizada.  
  
 [!code-xml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]