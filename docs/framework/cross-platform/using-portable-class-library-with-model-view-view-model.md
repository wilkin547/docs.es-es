---
description: 'Más información: Uso de la biblioteca de clases portable con Model-View-View Model'
title: Usar la Biblioteca de clases portable con Model-View-View Model
ms.date: 07/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
ms.openlocfilehash: 4eea099aaa515c2b7d9874fd6c6d5c4132c5e7a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "102402260"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="68a12-103">Usar la Biblioteca de clases portable con Model-View-View Model</span><span class="sxs-lookup"><span data-stu-id="68a12-103">Using Portable Class Library with Model-View-View Model</span></span>

<span data-ttu-id="68a12-104">Puede usar la [biblioteca de clases portable](portable-class-library.md) de .NET Framework para implementar el patrón Modelo-Vista-Modelo de vista (MVVM) y compartir ensamblados entre varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="68a12-104">You can use the .NET Framework [Portable Class Library](portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="68a12-105">MVVM es un patrón de aplicación que aísla la interfaz de usuario de la lógica de negocios subyacente.</span><span class="sxs-lookup"><span data-stu-id="68a12-105">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="68a12-106">Puede implementar las clases de modelo y modelo de vista en un proyecto de biblioteca de clases portable en Visual Studio 2012 y, a continuación, crear vistas personalizadas para distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="68a12-106">You can implement the model and view model classes in a Portable Class Library project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="68a12-107">Este enfoque le permite escribir el modelo de datos y la lógica de negocios solo una vez, además de usar ese código desde .NET Framework, Silverlight, Windows Phone y las aplicaciones de la Tienda Windows 8.x, tal como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="68a12-107">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and Windows 8.x Store apps, as shown in the following illustration.</span></span>

 ![Muestra la biblioteca de clases portable con ensamblados de uso compartido de MVVM entre plataformas.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 <span data-ttu-id="68a12-109">En este tema no se proporciona información general sobre el patrón MVVM.</span><span class="sxs-lookup"><span data-stu-id="68a12-109">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="68a12-110">Solo se proporciona información sobre cómo usar la biblioteca de clases portable para implementar MVVM.</span><span class="sxs-lookup"><span data-stu-id="68a12-110">It only provides information about how to use Portable Class Library to implement MVVM.</span></span> <span data-ttu-id="68a12-111">Para más información sobre MVVM, vea la [guía de inicio rápido de MVVM con la biblioteca Prism 5.0 para WPF](/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span><span class="sxs-lookup"><span data-stu-id="68a12-111">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="68a12-112">Clases que admiten MVVM</span><span class="sxs-lookup"><span data-stu-id="68a12-112">Classes That Support MVVM</span></span>

 <span data-ttu-id="68a12-113">Cuando el destino es .NET Framework 4.5, .NET para aplicaciones de la Tienda Windows 8.x, Silverlight o Windows Phone 7.5 para el proyecto de biblioteca de clases portable, están disponibles las siguientes clases para implementar el patrón MVVM:</span><span class="sxs-lookup"><span data-stu-id="68a12-113">When you target the .NET Framework 4.5, .NET for Windows 8.x Store apps, Silverlight, or Windows Phone 7.5 for your Portable Class Library project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="68a12-114">Clase <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-114"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="68a12-115">Clase <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-115"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="68a12-116">Clase <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-116"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="68a12-117">Clase <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-117"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="68a12-118">Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="68a12-119">Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-119"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="68a12-120">Clase <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-120"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="68a12-121">Clase <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-121"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="68a12-122">Clase <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-122"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="68a12-123">Clase <xref:System.Windows.Input.ICommand?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-123"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="68a12-124">Todas las clases del espacio de nombres <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="68a12-124">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="68a12-125">Implementación de MVVM</span><span class="sxs-lookup"><span data-stu-id="68a12-125">Implementing MVVM</span></span>

 <span data-ttu-id="68a12-126">Para implementar MVVM, normalmente se crea el modelo y el modelo de vista en un proyecto de biblioteca de clases portable, porque un proyecto de biblioteca de clases portable no puede hacer referencia a un proyecto no portable.</span><span class="sxs-lookup"><span data-stu-id="68a12-126">To implement MVVM, you typically create both the model and the view model in a Portable Class Library project, because a Portable Class Library project cannot reference a non-portable project.</span></span> <span data-ttu-id="68a12-127">El modelo y el modelo de vista pueden estar en el mismo proyecto o en proyectos independientes.</span><span class="sxs-lookup"><span data-stu-id="68a12-127">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="68a12-128">Si usa proyectos independientes, agregue una referencia desde el proyecto de modelo de vista al proyecto de modelo.</span><span class="sxs-lookup"><span data-stu-id="68a12-128">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="68a12-129">Después de compilar los proyectos de modelo y modelo de vista, se hace referencia a esos ensamblados en la aplicación que contiene la vista.</span><span class="sxs-lookup"><span data-stu-id="68a12-129">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="68a12-130">Si la vista interactúa solo con el modelo de vista, solo tiene que hacer referencia al ensamblado que contiene el modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="68a12-130">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="68a12-131">Modelado</span><span class="sxs-lookup"><span data-stu-id="68a12-131">Model</span></span>

 <span data-ttu-id="68a12-132">En el ejemplo siguiente se muestra una clase de modelo simplificada que puede residir en un proyecto de biblioteca de clases portable.</span><span class="sxs-lookup"><span data-stu-id="68a12-132">The following example shows a simplified model class that could reside in a Portable Class Library project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="68a12-133">En el ejemplo siguiente se muestra una forma sencilla de rellenar, recuperar y actualizar los datos en un proyecto de biblioteca de clases portable.</span><span class="sxs-lookup"><span data-stu-id="68a12-133">The following example shows a simple way to populate, retrieve, and update the data in a Portable Class Library project.</span></span> <span data-ttu-id="68a12-134">En una aplicación real, se recuperan los datos de un origen como un servicio de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="68a12-134">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="68a12-135">Modelo de vista</span><span class="sxs-lookup"><span data-stu-id="68a12-135">View Model</span></span>

 <span data-ttu-id="68a12-136">A menudo, se agrega una clase base para los modelos de vista al implementar el patrón MVVM.</span><span class="sxs-lookup"><span data-stu-id="68a12-136">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="68a12-137">En el ejemplo siguiente se muestra una clase base.</span><span class="sxs-lookup"><span data-stu-id="68a12-137">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="68a12-138">Una implementación de la interfaz <xref:System.Windows.Input.ICommand> se usa con frecuencia con el patrón MVVM.</span><span class="sxs-lookup"><span data-stu-id="68a12-138">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="68a12-139">En el siguiente ejemplo se muestra una implementación de la interfaz <xref:System.Windows.Input.ICommand>.</span><span class="sxs-lookup"><span data-stu-id="68a12-139">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="68a12-140">En el siguiente ejemplo se muestra un modelo de vista simplificado.</span><span class="sxs-lookup"><span data-stu-id="68a12-140">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="68a12-141">Ver</span><span class="sxs-lookup"><span data-stu-id="68a12-141">View</span></span>  

 <span data-ttu-id="68a12-142">Desde una aplicación .NET Framework 4.5, una aplicación de la Tienda Windows 8.x, una aplicación basada en Silverlight o una aplicación Windows Phone 7.5, puede hacer referencia al ensamblado que contiene los proyectos de modelo y modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="68a12-142">From a .NET Framework 4.5 app, Windows 8.x Store app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="68a12-143">A continuación, cree una vista que interactúe con el modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="68a12-143">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="68a12-144">En el ejemplo siguiente se muestra una aplicación simplificada de Windows Presentation Foundation (WPF) que recupera y actualiza los datos del modelo de vista.</span><span class="sxs-lookup"><span data-stu-id="68a12-144">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="68a12-145">Puede crear vistas similares en las aplicaciones de Silverlight, de Windows Phone o de la Tienda Windows 8.x.</span><span class="sxs-lookup"><span data-stu-id="68a12-145">You could create similar views in Silverlight, Windows Phone, or Windows 8.x Store apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="68a12-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="68a12-146">See also</span></span>

- [<span data-ttu-id="68a12-147">Biblioteca de clases portable</span><span class="sxs-lookup"><span data-stu-id="68a12-147">Portable Class Library</span></span>](portable-class-library.md)
