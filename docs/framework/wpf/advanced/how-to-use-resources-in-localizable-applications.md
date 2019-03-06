---
title: Filtrar Usar recursos en aplicaciones localizables
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: ad257e7703bcee8f71da78ad5928d7999365c38f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376170"
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="46727-102">Filtrar Usar recursos en aplicaciones localizables</span><span class="sxs-lookup"><span data-stu-id="46727-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="46727-103">Localizar significa adaptar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a distintas referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="46727-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="46727-104">Para ello, debe traducirse el texto, como títulos, leyendas, elementos de cuadro de lista, etc.</span><span class="sxs-lookup"><span data-stu-id="46727-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="46727-105">Para facilitar la traducción, los elementos que se van a traducir se recopilan en archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="46727-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="46727-106">Consulte [localizar una aplicación](how-to-localize-an-application.md) para obtener información sobre cómo crear un archivo de recursos para la localización.</span><span class="sxs-lookup"><span data-stu-id="46727-106">See [Localize an Application](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="46727-107">Para realizar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sea localizable, los desarrolladores deben compilar todos los recursos localizables en un ensamblado de recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="46727-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="46727-108">El ensamblado de recursos se localiza a distintos idiomas y el código subyacente utiliza la administración de recursos [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] para cargar.</span><span class="sxs-lookup"><span data-stu-id="46727-108">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="46727-109">Uno de los archivos necesarios para un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación es un archivo de proyecto (.proj).</span><span class="sxs-lookup"><span data-stu-id="46727-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="46727-110">Todos los recursos que se usan en la aplicación deben incluirse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="46727-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="46727-111">El ejemplo de código siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="46727-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46727-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46727-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="46727-113">Para usar un recurso en la aplicación, crear una instancia <xref:System.Resources.ResourceManager> y cargue el recurso que desea usar.</span><span class="sxs-lookup"><span data-stu-id="46727-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="46727-114">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="46727-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
