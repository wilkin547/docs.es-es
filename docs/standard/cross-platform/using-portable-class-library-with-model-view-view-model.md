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
ms.openlocfilehash: f5312177b9f437d9b5474d38fca80db6fc45245b
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77123680"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Usar la Biblioteca de clases portable con Model-View-View Model
Puede usar el .NET Framework [biblioteca de clases portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) para implementar el patrón Model-View-View Model (MVVM) y compartir ensamblados en varias plataformas.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 MVVM es un patrón de aplicación que aísla la interfaz de usuario de la lógica de negocios subyacente. Puede implementar las clases de modelo de modelo y vista en un proyecto de biblioteca de clases portable en Visual Studio 2012 y, a continuación, crear vistas personalizadas para distintas plataformas. Este enfoque le permite escribir el modelo de datos y la lógica de negocios solo una vez, y usar ese código desde .NET Framework, Silverlight, Windows Phone y las aplicaciones de la tienda Windows 8. x, tal como se muestra en la siguiente ilustración.

 ![Muestra la biblioteca de clases portable con ensamblados de uso compartido de MVVM entre plataformas.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 En este tema no se proporciona información general sobre el patrón MVVM. Solo proporciona información sobre cómo usar la biblioteca de clases portable para implementar MVVM. Para obtener más información sobre MVVM, consulte la guía de [Inicio rápido de MVVM con la biblioteca Prism 5,0 para WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).

## <a name="classes-that-support-mvvm"></a>Clases que admiten MVVM
 Cuando el destino es .NET Framework 4,5, .NET para aplicaciones de la tienda Windows 8. x, Silverlight o Windows Phone 7,5 para el proyecto de biblioteca de clases portable, están disponibles las siguientes clases para implementar el patrón MVVM:

- Clase <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>

- Clase <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>

- Clase <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>

- Clase <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>

- Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>

- Clase <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>

- Clase <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>

- Clase <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>

- Clase <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>

- Clase <xref:System.Windows.Input.ICommand?displayProperty=nameWithType>

- Todas las clases del espacio de nombres <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType>

## <a name="implementing-mvvm"></a>Implementar MVVM
 Para implementar MVVM, normalmente crea el modelo y el modelo de vista en un proyecto de biblioteca de clases portable, porque un proyecto de biblioteca de clases portable no puede hacer referencia a un proyecto no portátil. El modelo y el modelo de vista pueden estar en el mismo proyecto o en proyectos independientes. Si usa proyectos independientes, agregue una referencia desde el proyecto de modelo de vista al proyecto de modelo.

 Después de compilar los proyectos de modelo y vista de modelo, se hace referencia a esos ensamblados en la aplicación que contiene la vista. Si la vista interactúa solo con el modelo de vista, solo tiene que hacer referencia al ensamblado que contiene el modelo de vista.

### <a name="model"></a>Modelo
 En el ejemplo siguiente se muestra una clase de modelo simplificada que puede residir en un proyecto de biblioteca de clases portable.

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 En el ejemplo siguiente se muestra una forma sencilla de rellenar, recuperar y actualizar los datos en un proyecto de biblioteca de clases portable. En una aplicación real, se recuperan los datos de un origen como un servicio de Windows Communication Foundation (WCF).

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a>Modelo de vista
 A menudo se agrega una clase base para los modelos de vista al implementar el patrón MVVM. En el ejemplo siguiente se muestra una clase base.

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 Con frecuencia, se usa una implementación de la interfaz <xref:System.Windows.Input.ICommand> con el patrón MVVM. En el siguiente ejemplo se muestra una implementación de la interfaz <xref:System.Windows.Input.ICommand>.

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 En el ejemplo siguiente se muestra un modelo de vista simplificado.

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Ver  
 Desde una aplicación .NET Framework 4,5, una aplicación de la tienda Windows 8. x, una aplicación basada en Silverlight o la aplicación Windows Phone 7,5, puede hacer referencia al ensamblado que contiene los proyectos modelo y vista modelo.  A continuación, cree una vista que interactúe con el modelo de vista. En el ejemplo siguiente se muestra una aplicación simplificada de Windows Presentation Foundation (WPF) que recupera y actualiza los datos del modelo de vista. Puede crear vistas similares en las aplicaciones de la tienda Silverlight, Windows Phone o Windows 8. x.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>Consulte también

- [Biblioteca de clases portable](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
