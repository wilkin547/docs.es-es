---
title: 'Cómo: Usar un diccionario de recursos en el ámbito de aplicación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 5bfb3ed0304598a5acf4b7682bf4a4169c5153d1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459798"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="75c27-102">Cómo: Usar un diccionario de recursos en el ámbito de aplicación</span><span class="sxs-lookup"><span data-stu-id="75c27-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="75c27-103">En este ejemplo se muestra cómo definir y usar un diccionario de recursos personalizado de ámbito de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75c27-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75c27-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75c27-104">Example</span></span>  
 <span data-ttu-id="75c27-105"><xref:System.Windows.Application> expone un almacén de ámbito de aplicación para los recursos compartidos: <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="75c27-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="75c27-106">De forma predeterminada, la propiedad <xref:System.Windows.Application.Resources%2A> se inicializa con una instancia del tipo <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="75c27-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="75c27-107">Esta instancia se utiliza al obtener y establecer las propiedades del ámbito de aplicación mediante <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="75c27-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="75c27-108">Para obtener más información, consulte [Cómo: obtener y establecer un recurso de ámbito de aplicación](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="75c27-108">For more information, see [How to: Get and Set an Application-Scope Resource](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="75c27-109">Si tiene varios recursos que establece mediante <xref:System.Windows.Application.Resources%2A>, puede usar un diccionario de recursos personalizado para almacenar esos recursos y establecer <xref:System.Windows.Application.Resources%2A> con él en su lugar.</span><span class="sxs-lookup"><span data-stu-id="75c27-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="75c27-110">A continuación se muestra cómo declarar un diccionario de recursos personalizado mediante XAML.</span><span class="sxs-lookup"><span data-stu-id="75c27-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="75c27-111">El intercambio de diccionarios de recursos completos con <xref:System.Windows.Application.Resources%2A> permite admitir temas del ámbito de aplicación, donde cada tema se encapsula mediante un único Diccionario de recursos.</span><span class="sxs-lookup"><span data-stu-id="75c27-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="75c27-112">En el ejemplo siguiente se muestra cómo establecer <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="75c27-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="75c27-113">A continuación se muestra cómo puede obtener recursos del ámbito de aplicación del Diccionario de recursos expuesto por <xref:System.Windows.Application.Resources%2A> en XAML.</span><span class="sxs-lookup"><span data-stu-id="75c27-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="75c27-114">A continuación, se muestra cómo puede obtener también los recursos en el código.</span><span class="sxs-lookup"><span data-stu-id="75c27-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="75c27-115">Hay dos consideraciones que se deben tener en cuenta al utilizar <xref:System.Windows.Application.Resources%2A>.</span><span class="sxs-lookup"><span data-stu-id="75c27-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="75c27-116">En primer lugar, la *clave* del diccionario es un objeto, por lo que debe usar exactamente la misma instancia de objeto cuando ambos establecen y obtienen un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="75c27-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="75c27-117">(Tenga en cuenta que la clave distingue entre mayúsculas y minúsculas cuando se usa una cadena). En segundo lugar, el *valor* del diccionario es un objeto, por lo que tendrá que convertir el valor al tipo deseado al obtener un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="75c27-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75c27-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="75c27-118">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="75c27-119">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="75c27-119">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="75c27-120">Diccionarios de recursos combinados</span><span class="sxs-lookup"><span data-stu-id="75c27-120">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
