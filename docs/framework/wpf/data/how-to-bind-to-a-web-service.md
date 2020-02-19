---
title: 'Cómo: Enlazar a un servicio web'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 3a3f6edc974448ddab9fe30e97bdc1130d3b97dc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449977"
---
# <a name="how-to-bind-to-a-web-service"></a>Cómo: Enlazar a un servicio web
En este ejemplo se muestra cómo enlazar a objetos devueltos por llamadas al método de servicio Web.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el servicio de contenido de MSDN/TechNet Publishing System (MTPS) para recuperar la lista de idiomas admitidos por un documento especificado.  
  
 Antes de llamar a un servicio Web, debe crear una referencia a él. Para crear una referencia Web al servicio MTPS mediante Visual Studio, siga estos pasos:  
  
1. Abra el proyecto en Visual Studio.  
  
2. En el menú **proyecto** , haga clic en **Agregar referencia Web**.  
  
3. En el cuadro de diálogo, establezca la **dirección URL** en [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4. Presione **Go** y luego **Agregar referencia**.  
  
 A continuación, llame al método de servicio Web y establezca el <xref:System.Windows.FrameworkElement.DataContext%2A> del control o de la ventana correspondiente en el objeto devuelto. El método `GetContent` del servicio MTPS toma una referencia al objeto `getContentRequest`. Por lo tanto, en el ejemplo siguiente se configura primero un objeto de solicitud:  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Una vez establecido el <xref:System.Windows.FrameworkElement.DataContext%2A>, puede crear enlaces a las propiedades del objeto en el que se ha establecido el <xref:System.Windows.FrameworkElement.DataContext%2A>. En este ejemplo, la <xref:System.Windows.FrameworkElement.DataContext%2A> se establece en el objeto `getContentResponse` devuelto por el método `GetContent`. En el ejemplo siguiente, el <xref:System.Windows.Controls.ItemsControl> enlaza a y muestra los valores `locale` de `availableVersionsAndLocales` de `getContentResponse`.  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Para obtener información sobre la estructura de `getContentResponse`, consulte la [documentación del servicio de contenido](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Información general sobre orígenes de enlaces](binding-sources-overview.md)
- [Hacer que los datos estén disponibles para el enlace en XAML](how-to-make-data-available-for-binding-in-xaml.md)
