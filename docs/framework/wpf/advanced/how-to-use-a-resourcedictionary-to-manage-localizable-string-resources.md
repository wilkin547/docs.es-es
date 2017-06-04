---
title: "C&#243;mo: Usar ResourceDictionary para administrar recursos de cadenas localizables | Microsoft Docs"
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
  - "localización [WPF], empaquetar recursos de cadenas"
  - "empaquetar recursos de cadenas"
  - "ResourceDictionary [WPF]"
  - "recursos [WPF], empaquetar recursos de cadenas"
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Usar ResourceDictionary para administrar recursos de cadenas localizables
En este ejemplo se muestra cómo utilizar un objeto <xref:System.Windows.ResourceDictionary> para empaquetar los recursos de cadenas localizables para las aplicaciones de [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  
  
### Para utilizar un objeto ResourceDictionary a fin de administrar los recursos de cadenas localizables  
  
1.  Cree un objeto <xref:System.Windows.ResourceDictionary> que contenga las cadenas que desee localizar.  El siguiente fragmento de código muestra un ejemplo.  
  
     [!code-xml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     Este código define un recurso de cadena, `localizedMessage`, de tipo <xref:System.String>, del espacio de nombres <xref:System> de mscorlib.dll.  
  
2.  Agregue el objeto <xref:System.Windows.ResourceDictionary> a la aplicación, mediante el código siguiente.  
  
     [!code-xml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  Utilice el recurso de cadena desde el marcado, mediante un marcado [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] como el siguiente.  
  
     [!code-xml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  Utilice el recurso de cadena desde el código subyacente, mediante un código como el siguiente.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  Localice la aplicación.  Para obtener más información, consulte [Localizar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).