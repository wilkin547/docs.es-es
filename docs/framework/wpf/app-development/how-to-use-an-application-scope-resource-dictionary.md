---
title: Filtrar Usar un diccionario de recursos en el ámbito de aplicación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 6cd3e125b5b1a97f5851d4d1845e3e9e384e3d16
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748562"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="51fbf-102">Filtrar Usar un diccionario de recursos en el ámbito de aplicación</span><span class="sxs-lookup"><span data-stu-id="51fbf-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="51fbf-103">En este ejemplo se muestra cómo definir y usar un diccionario de recursos personalizado de ámbito de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="51fbf-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51fbf-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51fbf-104">Example</span></span>  
 <span data-ttu-id="51fbf-105"><xref:System.Windows.Application> expone un almacén de ámbito de la aplicación para los recursos compartidos: <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="51fbf-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="51fbf-106">De forma predeterminada, el <xref:System.Windows.Application.Resources%2A> propiedad se inicializa con una instancia de la <xref:System.Windows.ResourceDictionary> tipo.</span><span class="sxs-lookup"><span data-stu-id="51fbf-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="51fbf-107">Utilice esta instancia cuando obtenga y establezca las propiedades de ámbito de la aplicación mediante <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="51fbf-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="51fbf-108">Para obtener más información, vea [Cómo: Obtener y establecer un recurso de ámbito de la aplicación](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="51fbf-108">For more information, see [How to: Get and Set an Application-Scope Resource](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="51fbf-109">Si tiene varios recursos que establecen mediante <xref:System.Windows.Application.Resources%2A>, en su lugar, puede usar un diccionario de recursos personalizado para almacenar esos recursos y establecer <xref:System.Windows.Application.Resources%2A> con él en su lugar.</span><span class="sxs-lookup"><span data-stu-id="51fbf-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="51fbf-110">A continuación muestra cómo declarar un diccionario de recursos personalizado mediante XAML.</span><span class="sxs-lookup"><span data-stu-id="51fbf-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="51fbf-111">Intercambio de diccionarios de recursos completo mediante <xref:System.Windows.Application.Resources%2A> le permite admitir temas del ámbito de aplicación, donde cada tema se encapsula mediante un diccionario de recursos único.</span><span class="sxs-lookup"><span data-stu-id="51fbf-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="51fbf-112">En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="51fbf-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="51fbf-113">La siguiente muestra cómo puede obtener los recursos del ámbito de la aplicación desde el diccionario de recursos expuesto por <xref:System.Windows.Application.Resources%2A> en XAML.</span><span class="sxs-lookup"><span data-stu-id="51fbf-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="51fbf-114">A continuación, se muestra cómo puede obtener también los recursos en el código.</span><span class="sxs-lookup"><span data-stu-id="51fbf-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="51fbf-115">Existen dos consideraciones al usar <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="51fbf-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="51fbf-116">Primero, el diccionario *clave* es un objeto, por lo que debe usar exactamente la misma instancia del objeto al establecer y obtener un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="51fbf-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="51fbf-117">(Tenga en cuenta que la clave distingue mayúsculas de minúsculas cuando se utiliza una cadena). Segundo, el diccionario *valor* es un objeto, por lo que tendrá que convertir el valor al tipo deseado al obtener un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="51fbf-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51fbf-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="51fbf-118">See also</span></span>
- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="51fbf-119">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="51fbf-119">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [<span data-ttu-id="51fbf-120">Diccionarios de recursos combinados</span><span class="sxs-lookup"><span data-stu-id="51fbf-120">Merged Resource Dictionaries</span></span>](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)
