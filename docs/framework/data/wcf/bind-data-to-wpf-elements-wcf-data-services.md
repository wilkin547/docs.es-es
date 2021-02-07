---
description: 'Más información acerca de cómo: enlazar datos a elementos de Windows Presentation Foundation (Servicios de datos de WCF)'
title: 'Cómo: Enlazar datos a elementos de Windows Presentation Foundation (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: d6538ab0-0abe-426a-b9d9-e6f3a5ca2016
ms.openlocfilehash: 57ad03770681fbedf9b0d5afae82a0a2590f0bc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99766535"
---
# <a name="how-to-bind-data-to-windows-presentation-foundation-elements-wcf-data-services"></a>Cómo: Enlazar datos a elementos de Windows Presentation Foundation (Data Services de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Con Servicios de datos de WCF, puede enlazar elementos de Windows Presentation Foundation (WPF) como <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ComboBox> a una instancia de <xref:System.Data.Services.Client.DataServiceCollection%601> , que controla los eventos generados por los controles para mantener el <xref:System.Data.Services.Client.DataServiceContext> sincronizado con los cambios realizados en los datos de los controles. Para obtener más información, consulte [enlazar datos a controles](binding-data-to-controls-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de servicios de datos de WCF](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  

 El ejemplo siguiente es de la página de código subyacente de una página de lenguaje XAML que define la ventana `SalesOrders` en WPF. Cuando se carga la ventana, <xref:System.Data.Services.Client.DataServiceCollection%601> se crea una basada en el resultado de una consulta que devuelve los clientes, filtrados por país o región. Se cargan todas las páginas de este resultado paginado, junto con los pedidos relacionados, y se enlazan a la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> de <xref:System.Windows.Controls.StackPanel> que es el control de diseño raíz para la ventana de WPF. Para obtener más información, vea [cargar contenido diferido](loading-deferred-content-wcf-data-services.md).  
  
 [!code-csharp[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddata)]
 [!code-vb[Astoria Northwind Client#BindPagedData](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddata)]  
  
## <a name="example"></a>Ejemplo  

 El siguiente XAML define la ventana `SalesOrders` en WPF del ejemplo anterior.  
  
 [!code-xaml[Astoria Northwind Client#BindPagedDataXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml#bindpageddataxaml)]  
  
## <a name="example"></a>Ejemplo  

 El ejemplo siguiente es de la página de código subyacente de una página de lenguaje XAML que define la ventana `SalesOrders` en WPF. Cuando se carga la ventana, <xref:System.Data.Services.Client.DataServiceCollection%601> se crea una basada en el resultado de una consulta que devuelve los clientes con objetos relacionados, filtrados por país o región. Este resultado se enlaza a la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> de <xref:System.Windows.Controls.StackPanel> que es el control de diseño raíz para la ventana de WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#wpfdatabinding)]
 [!code-vb[Astoria Northwind Client#WpfDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#wpfdatabinding)]  
  
## <a name="example"></a>Ejemplo  

 El siguiente XAML define la ventana `SalesOrders` en WPF del ejemplo anterior.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#wpfdatabindingxaml)]
