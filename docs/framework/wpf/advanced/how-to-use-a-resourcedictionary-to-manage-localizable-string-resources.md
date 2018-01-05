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
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="e13e9-102">Cómo: Usar ResourceDictionary para administrar recursos de cadenas localizables</span><span class="sxs-lookup"><span data-stu-id="e13e9-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="e13e9-103">Este ejemplo muestra cómo utilizar un <xref:System.Windows.ResourceDictionary> para empaquetar recursos de cadenas localizables para [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="e13e9-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="e13e9-104">Usar ResourceDictionary para administrar recursos de cadenas localizables</span><span class="sxs-lookup"><span data-stu-id="e13e9-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1.  <span data-ttu-id="e13e9-105">Crear un <xref:System.Windows.ResourceDictionary> que contiene las cadenas que desea localizar.</span><span class="sxs-lookup"><span data-stu-id="e13e9-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="e13e9-106">En el código siguiente se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e13e9-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="e13e9-107">Este código define un recurso de cadena, `localizedMessage`, del tipo <xref:System.String>, desde el <xref:System> espacio de nombres en mscorlib.dll.</span><span class="sxs-lookup"><span data-stu-id="e13e9-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2.  <span data-ttu-id="e13e9-108">Agregue el <xref:System.Windows.ResourceDictionary> a la aplicación, utilizando el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e13e9-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  <span data-ttu-id="e13e9-109">Usar el recurso de cadena desde el marcado, mediante [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que en el siguiente.</span><span class="sxs-lookup"><span data-stu-id="e13e9-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  <span data-ttu-id="e13e9-110">Use el recurso de cadenas del código subyacente mediante código como el siguiente.</span><span class="sxs-lookup"><span data-stu-id="e13e9-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  <span data-ttu-id="e13e9-111">Localice la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e13e9-111">Localize the application.</span></span> <span data-ttu-id="e13e9-112">Para obtener más información, consulte [adaptar una aplicación](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="e13e9-112">For more information, see [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span></span>
