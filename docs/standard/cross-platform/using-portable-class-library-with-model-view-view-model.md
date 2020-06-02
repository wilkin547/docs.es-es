---
title: Usar la Biblioteca de clases portable con Model-View-View Model
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
ms.openlocfilehash: ff34b295ba443088115d470d8ade0c986ac1d856
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288854"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="495e6-102">Usar la Biblioteca de clases portable con Model-View-View Model</span><span class="sxs-lookup"><span data-stu-id="495e6-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="495e6-103">Puede usar el .NET Framework [biblioteca de clases portable](cross-platform-development-with-the-portable-class-library.md) para implementar el patrón Model-View-View Model (MVVM) y compartir ensamblados en varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="495e6-103">You can use the .NET Framework [Portable Class Library](cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="495e6-104">MVVM es un patrón de aplicación que aísla la interfaz de usuario de la lógica de negocios subyacente.</span><span class="sxs-lookup"><span data-stu-id="495e6-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="495e6-105">Puede implementar las clases de modelo de modelo y vista en un proyecto de biblioteca de clases portable en Visual Studio 2012 y, a continuación, crear vistas personalizadas para distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="495e6-105">You can implement the model and view model classes in a Portable Class Library project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="495e6-106">Este enfoque le permite escribir el modelo de datos y la lógica de negocios solo una vez, y usar ese código desde .NET Framework, Silverlight, Windows Phone y las aplicaciones de la tienda Windows 8. x, tal como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="495e6-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and Windows 8.x Store apps, as shown in the following illustration.</span></span>

 ![Muestra la biblioteca de clases portable con ensamblados de uso compartido de MVVM entre plataformas.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 <span data-ttu-id="495e6-108">En este tema no se proporciona información general sobre el patrón MVVM.</span><span class="sxs-lookup"><span data-stu-id="495e6-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="495e6-109">Solo proporciona información sobre cómo usar la biblioteca de clases portable para implementar MVVM.</span><span class="sxs-lookup"><span data-stu-id="495e6-109">It only provides information about how to use Portable Class Library to implement MVVM.</span></span> <span data-ttu-id="495e6-110">Para obtener más información sobre MVVM, consulte la guía de [Inicio rápido de MVVM con la biblioteca Prism 5,0 para WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span><span class="sxs-lookup"><span data-stu-id="495e6-110">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="495e6-111">Clases que admiten MVVM</span><span class="sxs-lookup"><span data-stu-id="495e6-111">Classes That Support MVVM</span></span>
 <span data-ttu-id="495e6-112">Cuando el destino es .NET Framework 4,5, .NET para aplicaciones de la tienda Windows 8. x, Silverlight o Windows Phone 7,5 para el proyecto de biblioteca de clases portable, están disponibles las siguientes clases para implementar el patrón MVVM:</span><span class="sxs-lookup"><span data-stu-id="495e6-112">When you target the .NET Framework 4.5, .NET for Windows 8.x Store apps, Silverlight, or Windows Phone 7.5 for your Portable Class Library project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="495e6-113">Clase <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="495e6-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="495e6-114">Clase <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="495e6-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="495e6-115">Clase <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="495e6-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="495e6-116">Clase <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="495e6-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="495e6-117">Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="495e6-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="495e6-118">Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="495e6-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="495e6-119">Clase <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="495e6-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="495e6-120">Clase <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="495e6-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="495e6-121">Clase <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="495e6-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="495e6-122">Clase <xref:System.Windows.Input.ICommand?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="495e6-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="495e6-123">Todas las clases del <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="495e6-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="495e6-124">Implementar MVVM</span><span class="sxs-lookup"><span data-stu-id="495e6-124">Implementing MVVM</span></span>
 <span data-ttu-id="495e6-125">Para implementar MVVM, normalmente crea el modelo y el modelo de vista en un proyecto de biblioteca de clases portable, porque un proyecto de biblioteca de clases portable no puede hacer referencia a un proyecto no portátil.</span><span class="sxs-lookup"><span data-stu-id="495e6-125">To implement MVVM, you typically create both the model and the view model in a Portable Class Library project, because a Portable Class Library project cannot reference a non-portable project.</span></span> <span data-ttu-id="495e6-126">El modelo y el modelo de vista pueden estar en el mismo proyecto o en proyectos independientes.</span><span class="sxs-lookup"><span data-stu-id="495e6-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="495e6-127">Si usa proyectos independientes, agregue una referencia desde el proyecto de modelo de vista al proyecto de modelo.</span><span class="sxs-lookup"><span data-stu-id="495e6-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="495e6-128">Después de compilar los proyectos de modelo y vista de modelo, se hace referencia a esos ensamblados en la aplicación que contiene la vista.</span><span class="sxs-lookup"><span data-stu-id="495e6-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="495e6-129">Si la vista interactúa solo con el modelo de vista, solo tiene que hacer referencia al ensamblado que contiene el modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="495e6-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="495e6-130">Modelo</span><span class="sxs-lookup"><span data-stu-id="495e6-130">Model</span></span>
 <span data-ttu-id="495e6-131">En el ejemplo siguiente se muestra una clase de modelo simplificada que puede residir en un proyecto de biblioteca de clases portable.</span><span class="sxs-lookup"><span data-stu-id="495e6-131">The following example shows a simplified model class that could reside in a Portable Class Library project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="495e6-132">En el ejemplo siguiente se muestra una forma sencilla de rellenar, recuperar y actualizar los datos en un proyecto de biblioteca de clases portable.</span><span class="sxs-lookup"><span data-stu-id="495e6-132">The following example shows a simple way to populate, retrieve, and update the data in a Portable Class Library project.</span></span> <span data-ttu-id="495e6-133">En una aplicación real, se recuperan los datos de un origen como un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="495e6-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="495e6-134">Modelo de vista</span><span class="sxs-lookup"><span data-stu-id="495e6-134">View Model</span></span>
 <span data-ttu-id="495e6-135">A menudo se agrega una clase base para los modelos de vista al implementar el patrón MVVM.</span><span class="sxs-lookup"><span data-stu-id="495e6-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="495e6-136">En el ejemplo siguiente se muestra una clase base.</span><span class="sxs-lookup"><span data-stu-id="495e6-136">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="495e6-137">Una implementación de la <xref:System.Windows.Input.ICommand> interfaz se usa con frecuencia con el patrón MVVM.</span><span class="sxs-lookup"><span data-stu-id="495e6-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="495e6-138">En el siguiente ejemplo se muestra una implementación de la interfaz <xref:System.Windows.Input.ICommand>.</span><span class="sxs-lookup"><span data-stu-id="495e6-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="495e6-139">En el ejemplo siguiente se muestra un modelo de vista simplificado.</span><span class="sxs-lookup"><span data-stu-id="495e6-139">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="495e6-140">Ver</span><span class="sxs-lookup"><span data-stu-id="495e6-140">View</span></span>  
 <span data-ttu-id="495e6-141">Desde una aplicación .NET Framework 4,5, una aplicación de la tienda Windows 8. x, una aplicación basada en Silverlight o la aplicación Windows Phone 7,5, puede hacer referencia al ensamblado que contiene los proyectos modelo y vista modelo.</span><span class="sxs-lookup"><span data-stu-id="495e6-141">From a .NET Framework 4.5 app, Windows 8.x Store app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="495e6-142">A continuación, cree una vista que interactúe con el modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="495e6-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="495e6-143">En el ejemplo siguiente se muestra una aplicación simplificada de Windows Presentation Foundation (WPF) que recupera y actualiza los datos del modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="495e6-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="495e6-144">Puede crear vistas similares en las aplicaciones de la tienda Silverlight, Windows Phone o Windows 8. x.</span><span class="sxs-lookup"><span data-stu-id="495e6-144">You could create similar views in Silverlight, Windows Phone, or Windows 8.x Store apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="495e6-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="495e6-145">See also</span></span>

- [<span data-ttu-id="495e6-146">Biblioteca de clases portable</span><span class="sxs-lookup"><span data-stu-id="495e6-146">Portable Class Library</span></span>](cross-platform-development-with-the-portable-class-library.md)
