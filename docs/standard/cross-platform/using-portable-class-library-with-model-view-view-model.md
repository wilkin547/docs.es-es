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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7b42f20509b34b934418ed8e870a60713def7387
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48842585"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="04d2e-102">Usar la Biblioteca de clases portable con Model-View-View Model</span><span class="sxs-lookup"><span data-stu-id="04d2e-102">Using Portable Class Library with Model-View-View Model</span></span>
<span data-ttu-id="04d2e-103">Puede usar .NET Framework [biblioteca de clases Portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) para implementar el patrón Model-View-View Model (MVVM) y compartir los ensamblados en varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="04d2e-103">You can use the .NET Framework [Portable Class Library](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="04d2e-104">MVVM es un patrón de aplicación que aísla la interfaz de usuario de la lógica empresarial subyacente.</span><span class="sxs-lookup"><span data-stu-id="04d2e-104">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="04d2e-105">Puede implementar el modelo y ver las clases de modelo en un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] del proyecto en Visual Studio 2012 y, a continuación, crear vistas personalizadas para distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="04d2e-105">You can implement the model and view model classes in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="04d2e-106">Este enfoque le permite escribir los datos de modelo y lógica de negocios de una sola vez y usar ese código a partir de .NET Framework, Silverlight y Windows Phone, y [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] las aplicaciones, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="04d2e-106">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps, as shown in the following illustration.</span></span>

 <span data-ttu-id="04d2e-107">![Portable con diagrama de MVVM](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span><span class="sxs-lookup"><span data-stu-id="04d2e-107">![Portable with MVVM diagram](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")</span></span>

 <span data-ttu-id="04d2e-108">En este tema no proporciona información general sobre el patrón MVVM.</span><span class="sxs-lookup"><span data-stu-id="04d2e-108">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="04d2e-109">Sólo proporciona información sobre cómo usar [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] para implementar MVVM.</span><span class="sxs-lookup"><span data-stu-id="04d2e-109">It only provides information about how to use [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] to implement MVVM.</span></span> <span data-ttu-id="04d2e-110">Para obtener más información acerca de MVVM, consulte el [inicio rápido de MVVM](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx).</span><span class="sxs-lookup"><span data-stu-id="04d2e-110">For more information about MVVM, see the [MVVM Quickstart](https://msdn.microsoft.com/library/gg430869(v=PandP.40).aspx).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="04d2e-111">Clases que admiten MVVM</span><span class="sxs-lookup"><span data-stu-id="04d2e-111">Classes That Support MVVM</span></span>
 <span data-ttu-id="04d2e-112">Cuando el destino es el [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight o Windows Phone 7.5 para su [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proyecto, existen las siguientes clases para implementar el patrón MVVM:</span><span class="sxs-lookup"><span data-stu-id="04d2e-112">When you target the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight, or Windows Phone 7.5 for your [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, the following classes are available for implementing the MVVM pattern:</span></span>

-   <span data-ttu-id="04d2e-113">Clase <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="04d2e-113"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

-   <span data-ttu-id="04d2e-114">Clase <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="04d2e-114"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

-   <span data-ttu-id="04d2e-115">Clase <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="04d2e-115"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

-   <span data-ttu-id="04d2e-116">Clase <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="04d2e-116"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

-   <span data-ttu-id="04d2e-117">Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="04d2e-117"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

-   <span data-ttu-id="04d2e-118">Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="04d2e-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

-   <span data-ttu-id="04d2e-119">Clase <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="04d2e-119"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

-   <span data-ttu-id="04d2e-120">Clase <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="04d2e-120"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

-   <span data-ttu-id="04d2e-121">Clase <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="04d2e-121"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

-   <span data-ttu-id="04d2e-122">Clase <xref:System.Windows.Input.ICommand?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="04d2e-122"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

-   <span data-ttu-id="04d2e-123">Todas las clases en el <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="04d2e-123">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="04d2e-124">Implementar MVVM</span><span class="sxs-lookup"><span data-stu-id="04d2e-124">Implementing MVVM</span></span>
 <span data-ttu-id="04d2e-125">Para implementar MVVM, normalmente crea el modelo y el modelo de vista en un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proyecto, porque un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proyecto no puede hacer referencia a un proyecto no portable.</span><span class="sxs-lookup"><span data-stu-id="04d2e-125">To implement MVVM, you typically create both the model and the view model in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project, because a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project cannot reference a non-portable project.</span></span> <span data-ttu-id="04d2e-126">El modelo y el modelo de vista pueden estar en el mismo proyecto o en proyectos independientes.</span><span class="sxs-lookup"><span data-stu-id="04d2e-126">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="04d2e-127">Si utiliza proyectos independientes, agregue una referencia desde el proyecto de modelo de vista al proyecto de modelo.</span><span class="sxs-lookup"><span data-stu-id="04d2e-127">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="04d2e-128">Después de compilar el modelo y ver los proyectos de modelos, hacer referencia a esos ensamblados en la aplicación que contiene la vista.</span><span class="sxs-lookup"><span data-stu-id="04d2e-128">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="04d2e-129">Si la vista interactúa con el modelo de vista, solo debe hacer referencia al ensamblado que contiene el modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="04d2e-129">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="04d2e-130">Modelo</span><span class="sxs-lookup"><span data-stu-id="04d2e-130">Model</span></span>
 <span data-ttu-id="04d2e-131">El ejemplo siguiente muestra una clase de modelo simplificado que podría residir en un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="04d2e-131">The following example shows a simplified model class that could reside in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="04d2e-132">El ejemplo siguiente muestra una manera sencilla para rellenar, recuperar y actualizar los datos en un [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] proyecto.</span><span class="sxs-lookup"><span data-stu-id="04d2e-132">The following example shows a simple way to populate, retrieve, and update the data in a [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] project.</span></span> <span data-ttu-id="04d2e-133">En una aplicación real, puede recuperar los datos de un origen como un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="04d2e-133">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="04d2e-134">Modelo de vista</span><span class="sxs-lookup"><span data-stu-id="04d2e-134">View Model</span></span>
 <span data-ttu-id="04d2e-135">Con frecuencia se agrega una clase base para los modelos de vista al implementar el patrón MVVM.</span><span class="sxs-lookup"><span data-stu-id="04d2e-135">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="04d2e-136">El ejemplo siguiente muestra una clase base.</span><span class="sxs-lookup"><span data-stu-id="04d2e-136">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="04d2e-137">Una implementación de la <xref:System.Windows.Input.ICommand> interfaz se suele utilizar con el patrón MVVM.</span><span class="sxs-lookup"><span data-stu-id="04d2e-137">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="04d2e-138">En el siguiente ejemplo se muestra una implementación de la interfaz <xref:System.Windows.Input.ICommand>.</span><span class="sxs-lookup"><span data-stu-id="04d2e-138">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="04d2e-139">El ejemplo siguiente muestra un modelo de vista simplificada.</span><span class="sxs-lookup"><span data-stu-id="04d2e-139">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="04d2e-140">Ver</span><span class="sxs-lookup"><span data-stu-id="04d2e-140">View</span></span>  
 <span data-ttu-id="04d2e-141">Desde un [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones, aplicaciones basadas en Silverlight o aplicaciones de Windows Phone 7.5, puede hacer referencia al ensamblado que contiene el modelo y ver los proyectos de modelos.</span><span class="sxs-lookup"><span data-stu-id="04d2e-141">From a [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] app, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="04d2e-142">A continuación, crea una vista que interactúa con el modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="04d2e-142">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="04d2e-143">El ejemplo siguiente muestra una aplicación de Windows Presentation Foundation (WPF) simplificada que recupera y actualiza los datos desde el modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="04d2e-143">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="04d2e-144">Puede crear vistas similares en Silverlight, Windows Phone, o [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="04d2e-144">You could create similar views in Silverlight, Windows Phone, or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="04d2e-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="04d2e-145">See also</span></span>

- [<span data-ttu-id="04d2e-146">Biblioteca de clases portable</span><span class="sxs-lookup"><span data-stu-id="04d2e-146">Portable Class Library</span></span>](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
