---
title: Filtrar Usar un objeto ResourceDictionary a fin de administrar los recursos de cadenas localizables
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
ms.openlocfilehash: b56a307ed31fc8f7573215eac70350ac5e4b9de1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311323"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="0bd66-102">Filtrar Usar un objeto ResourceDictionary a fin de administrar los recursos de cadenas localizables</span><span class="sxs-lookup"><span data-stu-id="0bd66-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="0bd66-103">En este ejemplo se muestra cómo usar un <xref:System.Windows.ResourceDictionary> para empaquetar recursos de cadenas localizables para aplicaciones Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="0bd66-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="0bd66-104">Usar ResourceDictionary para administrar recursos de cadenas localizables</span><span class="sxs-lookup"><span data-stu-id="0bd66-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1. <span data-ttu-id="0bd66-105">Crear un <xref:System.Windows.ResourceDictionary> que contiene las cadenas que quiere localizar.</span><span class="sxs-lookup"><span data-stu-id="0bd66-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="0bd66-106">En el código siguiente se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0bd66-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="0bd66-107">Este código define un recurso de cadena, `localizedMessage`, del tipo <xref:System.String>, desde el <xref:System> espacio de nombres en mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="0bd66-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2. <span data-ttu-id="0bd66-108">Agregue el <xref:System.Windows.ResourceDictionary> a la aplicación, utilizando el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="0bd66-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3. <span data-ttu-id="0bd66-109">Usar el recurso de cadena de marcado, con [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="0bd66-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4. <span data-ttu-id="0bd66-110">Use el recurso de cadenas del código subyacente mediante código como el siguiente.</span><span class="sxs-lookup"><span data-stu-id="0bd66-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5. <span data-ttu-id="0bd66-111">Localice la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0bd66-111">Localize the application.</span></span> <span data-ttu-id="0bd66-112">Para obtener más información, consulte [localizar una aplicación](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="0bd66-112">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>
