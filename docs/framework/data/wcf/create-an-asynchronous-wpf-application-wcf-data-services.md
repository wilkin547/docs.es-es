---
title: 'Cómo: Crear una aplicación asincrónica de Windows Presentation Framework (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
ms.openlocfilehash: d6acf3cbbfce491ebf98513b116d76ef9feb6d08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Cómo: Crear una aplicación asincrónica de Windows Presentation Framework (Data Services de WCF)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede enlazar los datos obtenidos de un servicio de datos a los elementos de la interfaz de usuario de una aplicación de Windows Presentation Framework (WPF). Para obtener más información, consulte [enlazar datos a controles](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md). También puede ejecutar operaciones en el servicio de datos de manera asincrónica, lo que permite a la aplicación pueda continuar responder mientras se espera una respuesta a una solicitud de servicio de datos. Las aplicaciones para Silverlight deben tener acceso al servicio de datos de forma asincrónica. Para obtener más información, consulte [operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 En este tema se muestra cómo tener acceso a un servicio de datos de forma asincrónica y enlazar los resultados a los elementos de una aplicación WPF. En los ejemplos de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos del cliente generadas automáticamente. Se crean este servicio y las clases de datos de cliente al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 El código XAML siguiente define la ventana de la aplicación WPF.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Ejemplo  
 La página de codigos subyacente siguiente para el archivo XAML ejecuta una consulta asincrónica usando el servicio de datos y enlaza los resultados a los elementos de la ventana de WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
