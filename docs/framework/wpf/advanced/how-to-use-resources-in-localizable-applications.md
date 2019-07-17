---
title: Procedimiento Usar recursos en aplicaciones localizables
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 3634bb72cbacfb02b0a1230a47a1664cb8ce5009
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238460"
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="f785e-102">Procedimiento Usar recursos en aplicaciones localizables</span><span class="sxs-lookup"><span data-stu-id="f785e-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="f785e-103">Localizar significa adaptar una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a distintas referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="f785e-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="f785e-104">Para ello, debe traducirse el texto, como títulos, leyendas, elementos de cuadro de lista, etc.</span><span class="sxs-lookup"><span data-stu-id="f785e-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="f785e-105">Para facilitar la traducción, los elementos que se van a traducir se recopilan en archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="f785e-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="f785e-106">Consulte [localizar una aplicación](how-to-localize-an-application.md) para obtener información sobre cómo crear un archivo de recursos para la localización.</span><span class="sxs-lookup"><span data-stu-id="f785e-106">See [Localize an Application](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="f785e-107">Para realizar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sea localizable, los desarrolladores deben compilar todos los recursos localizables en un ensamblado de recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f785e-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="f785e-108">El ensamblado de recursos se localiza a distintos idiomas y el código subyacente utiliza la API de administración de recursos para cargar.</span><span class="sxs-lookup"><span data-stu-id="f785e-108">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span> <span data-ttu-id="f785e-109">Uno de los archivos necesarios para un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación es un archivo de proyecto (.proj).</span><span class="sxs-lookup"><span data-stu-id="f785e-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="f785e-110">Todos los recursos que se usan en la aplicación deben incluirse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f785e-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="f785e-111">El ejemplo de código siguiente muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f785e-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f785e-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f785e-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="f785e-113">Para usar un recurso en la aplicación, crear una instancia <xref:System.Resources.ResourceManager> y cargue el recurso que desea usar.</span><span class="sxs-lookup"><span data-stu-id="f785e-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="f785e-114">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f785e-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
