---
title: "Cómo: Usar ResourceDictionary para administrar recursos de cadenas localizables"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9fba115ea8c954da177afcacbf679f41474e2b68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Cómo: Usar ResourceDictionary para administrar recursos de cadenas localizables
Este ejemplo muestra cómo utilizar un <xref:System.Windows.ResourceDictionary> para empaquetar recursos de cadenas localizables para [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] las aplicaciones.  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Usar ResourceDictionary para administrar recursos de cadenas localizables  
  
1.  Crear un <xref:System.Windows.ResourceDictionary> que contiene las cadenas que desea localizar. En el código siguiente se muestra un ejemplo.  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     Este código define un recurso de cadena, `localizedMessage`, del tipo <xref:System.String>, desde el <xref:System> espacio de nombres en mscorlib.dll.  
  
2.  Agregue el <xref:System.Windows.ResourceDictionary> a la aplicación, utilizando el código siguiente.  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  Usar el recurso de cadena desde el marcado, mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que en el siguiente.  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  Use el recurso de cadenas del código subyacente mediante código como el siguiente.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  Localice la aplicación. Para obtener más información, consulte [adaptar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).
