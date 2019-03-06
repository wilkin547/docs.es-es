---
title: Procedimiento Utilizar un objeto ResourceDictionary a fin de administrar los recursos de cadenas localizables
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
ms.openlocfilehash: e28086d8c97070b854ebdea35fe347c64c5cd7ac
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377942"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Procedimiento Utilizar un objeto ResourceDictionary a fin de administrar los recursos de cadenas localizables
En este ejemplo se muestra cómo usar un <xref:System.Windows.ResourceDictionary> para empaquetar recursos de cadenas localizables para aplicaciones Windows Presentation Foundation (WPF).  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>Usar ResourceDictionary para administrar recursos de cadenas localizables  
  
1.  Crear un <xref:System.Windows.ResourceDictionary> que contiene las cadenas que quiere localizar. En el código siguiente se muestra un ejemplo.  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     Este código define un recurso de cadena, `localizedMessage`, del tipo <xref:System.String>, desde el <xref:System> espacio de nombres en mscorlib.dll.  
  
2.  Agregue el <xref:System.Windows.ResourceDictionary> a la aplicación, utilizando el código siguiente.  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  Usar el recurso de cadena de marcado, con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] similar al siguiente.  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  Use el recurso de cadenas del código subyacente mediante código como el siguiente.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  Localice la aplicación. Para obtener más información, consulte [localizar una aplicación](how-to-localize-an-application.md).
