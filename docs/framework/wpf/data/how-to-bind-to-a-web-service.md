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
ms.openlocfilehash: 84c5aee8d2bc7d31ebcfee98930d9a0847c527d5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397090"
---
# <a name="how-to-bind-to-a-web-service"></a>Cómo: Enlazar a un servicio web
En este ejemplo se muestra cómo enlazar a los objetos devueltos por llamadas al método de servicios Web.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el [MSDN/TechNet Publishing System (MTPS) Content Service](https://go.microsoft.com/fwlink/?LinkId=95677) para recuperar la lista de idiomas admitidos por un documento especificado.  
  
 Antes de llamar a un servicio Web, deberá crear una referencia a él. Para crear una referencia Web al servicio MTPS utilizando [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], siga los pasos siguientes:  
  
1.  Abra el proyecto en [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].  
  
2.  Desde el **proyecto** menú, haga clic en **Agregar referencia Web**.  
  
3.  En el cuadro de diálogo, establezca el **URL** a [ http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl ](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).  
  
4.  Presione **vaya** y, a continuación, **Agregar referencia**.  
  
 A continuación, llama al método de servicio Web y establezca el <xref:System.Windows.FrameworkElement.DataContext%2A> del control adecuado o la ventana en el objeto devuelto. El **GetContent** método del servicio MTPS toma una referencia a la **getContentRequest** objeto. Por lo tanto, el ejemplo siguiente se establece primero un objeto de solicitud:  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 Después de la <xref:System.Windows.FrameworkElement.DataContext%2A> se haya configurado, puede crear enlaces a las propiedades del objeto que el <xref:System.Windows.FrameworkElement.DataContext%2A> se ha establecido en. En este ejemplo, el <xref:System.Windows.FrameworkElement.DataContext%2A> está establecido en el **getContentResponse** objeto devuelto por la **GetContent** método. En el ejemplo siguiente, la <xref:System.Windows.Controls.ItemsControl> enlaza y muestra el **configuración regional** valores de **availableVersionsAndLocales** de **getContentResponse**.  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 Para obtener información sobre la estructura de **getContentResponse**, consulte [documentación del servicio contenido](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Información general sobre orígenes de enlaces](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [Hacer que los datos estén disponibles para el enlace en XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
