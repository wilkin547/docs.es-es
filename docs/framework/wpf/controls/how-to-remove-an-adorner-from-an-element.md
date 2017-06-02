---
title: "C&#243;mo: Quitar un adorno de un elemento | Microsoft Docs"
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
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Quitar un adorno de un elemento
En este ejemplo se muestra cómo quitar mediante programación un adorno concreto del elemento <xref:System.Windows.UIElement> especificado.  
  
## Ejemplo  
 En este ejemplo de código detallado se quita el primer adorno en la matriz de adornos devuelta por <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  Este recupera los adornos de un elemento <xref:System.Windows.UIElement> denominado *myTextBox*.  Si el elemento especificado en la llamada a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> no tiene ningún adorno, se devuelve `null`.  En este código se comprueba explícitamente si la matriz es null y resulta especialmente adecuado para aplicaciones en que cabe esperar que una matriz sea null con relativa frecuencia.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## Ejemplo  
 Este ejemplo de código comprimido es funcionalmente equivalente al ejemplo detallado mostrado anteriormente.  En este código no se comprueba explícitamente si la matriz es null, por lo que es posible que se inicie una excepción <xref:System.NullReferenceException>.  Este código es más apropiado para aplicaciones en que no sea frecuente que una matriz sea null.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## Vea también  
 [Información general sobre adornos](../../../../docs/framework/wpf/controls/adorners-overview.md)