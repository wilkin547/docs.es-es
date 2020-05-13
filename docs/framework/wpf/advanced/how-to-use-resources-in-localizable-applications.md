---
title: 'Cómo: Usar recursos en aplicaciones localizables'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212480"
---
# <a name="how-to-use-resources-in-localizable-apps"></a><span data-ttu-id="1bdf3-102">Cómo: usar recursos en aplicaciones localizables</span><span class="sxs-lookup"><span data-stu-id="1bdf3-102">How to: Use resources in localizable apps</span></span>

<span data-ttu-id="1bdf3-103">La localización significa adaptar una interfaz de usuario a diferentes referencias culturales.</span><span class="sxs-lookup"><span data-stu-id="1bdf3-103">Localization means to adapt a user interface to different cultures.</span></span> <span data-ttu-id="1bdf3-104">Para ello, se debe traducir el texto, como títulos, leyendas y elementos del cuadro de lista.</span><span class="sxs-lookup"><span data-stu-id="1bdf3-104">To do this, text such as titles, captions, and list box items must be translated.</span></span> <span data-ttu-id="1bdf3-105">Para facilitar la traducción, los elementos que se van a traducir se recopilan en archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="1bdf3-105">To make translation easier, the items to be translated are collected into resource files.</span></span> <span data-ttu-id="1bdf3-106">Consulte [localizar una aplicación](how-to-localize-an-application.md) para obtener información sobre cómo crear un archivo de recursos para la localización.</span><span class="sxs-lookup"><span data-stu-id="1bdf3-106">See [Localize an app](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="1bdf3-107">Para que una aplicación WPF sea localizable, los desarrolladores deben compilar todos los recursos localizables en un ensamblado de recursos.</span><span class="sxs-lookup"><span data-stu-id="1bdf3-107">To make a WPF application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="1bdf3-108">El ensamblado de recursos se localiza en idiomas diferentes y el código subyacente usa la API de administración de recursos para cargar.</span><span class="sxs-lookup"><span data-stu-id="1bdf3-108">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span>

## <a name="example"></a><span data-ttu-id="1bdf3-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bdf3-109">Example</span></span>

<span data-ttu-id="1bdf3-110">Uno de los archivos necesarios para una aplicación WPF es un archivo de proyecto (. proj).</span><span class="sxs-lookup"><span data-stu-id="1bdf3-110">One of the files required for a WPF application is a project file (.proj).</span></span> <span data-ttu-id="1bdf3-111">Todos los recursos que se utilizan en la aplicación deben incluirse en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="1bdf3-111">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="1bdf3-112">En el siguiente ejemplo de XAML se muestra esto.</span><span class="sxs-lookup"><span data-stu-id="1bdf3-112">The following XAML example shows this.</span></span>

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

<span data-ttu-id="1bdf3-113">Para usar un recurso en la aplicación, cree una instancia <xref:System.Resources.ResourceManager> y cargue el recurso que desea usar.</span><span class="sxs-lookup"><span data-stu-id="1bdf3-113">To use a resource in your application, instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="1bdf3-114">En el siguiente código de C# se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="1bdf3-114">The following C# code demonstrates how to do this.</span></span>

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a><span data-ttu-id="1bdf3-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bdf3-115">See also</span></span>

- [<span data-ttu-id="1bdf3-116">Localizar una aplicación</span><span class="sxs-lookup"><span data-stu-id="1bdf3-116">Localize an app</span></span>](how-to-localize-an-application.md)
