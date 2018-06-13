---
title: 'Cómo: Usar ResourceDictionary para administrar recursos de cadenas localizables'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: 76ff3f688b5d3e7122254990076edb21fe6ae119
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544503"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Cómo: Usar ResourceDictionary para administrar recursos de cadenas localizables
Este ejemplo muestra cómo utilizar un <xref:System.Windows.ResourceDictionary> para empaquetar recursos de cadenas localizables para las aplicaciones de Windows Presentation Foundation (WPF).  
  
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
