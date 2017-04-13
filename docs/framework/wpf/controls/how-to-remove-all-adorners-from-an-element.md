---
title: "C&#243;mo: Quitar todos los adornos de un elemento | Microsoft Docs"
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
  - "adornos, quitar"
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Quitar todos los adornos de un elemento
En este ejemplo se muestra cómo quitar mediante programación todos los adornos de un elemento <xref:System.Windows.UIElement> especificado.  
  
## Ejemplo  
 En este ejemplo de código detallado se quitan todos los adornos en la matriz de adornos devuelta por <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  Este recupera los adornos de un elemento <xref:System.Windows.UIElement> denominado *myTextBox*.  Si el elemento especificado en la llamada a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> no tiene ningún adorno, se devuelve `null`.  En este código se comprueba explícitamente si la matriz es null y resulta especialmente adecuado para aplicaciones en que cabe esperar que una matriz sea null con relativa frecuencia.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## Ejemplo  
 Este ejemplo de código comprimido es funcionalmente equivalente al ejemplo detallado mostrado anteriormente.  En este código no se comprueba explícitamente si la matriz es null, por lo que es posible que se inicie una excepción <xref:System.NullReferenceException>.  Este código es más apropiado para aplicaciones en que no sea frecuente que una matriz sea null.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## Vea también  
 [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md)