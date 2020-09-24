---
title: 'Cómo: Crear una aplicación asincrónica de Windows Presentation Framework (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
ms.openlocfilehash: 67f6e27e4042e1cddbef8b99a2235e1a21d270d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152747"
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Cómo: Crear una aplicación asincrónica de Windows Presentation Framework (Data Services de WCF)

Con WCF Data Services, puede enlazar datos obtenidos de un servicio de datos a un elemento de la interfaz de usuario de una aplicación de Windows Presentation Framework (WPF). Para obtener más información, consulte [enlazar datos a controles](binding-data-to-controls-wcf-data-services.md). También puede ejecutar operaciones en el servicio de datos de una manera asincrónica, lo que permite que la aplicación siga respondiendo mientras se espera una respuesta a una solicitud de servicio de datos. Las aplicaciones para Silverlight deben tener acceso al servicio de datos de forma asincrónica. Para obtener más información, vea [operaciones asincrónicas](asynchronous-operations-wcf-data-services.md).  
  
 En este tema se muestra cómo tener acceso a un servicio de datos de forma asincrónica y enlazar los resultados a los elementos de una aplicación WPF. En los ejemplos de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos del cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  

 El código XAML siguiente define la ventana de la aplicación WPF.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Ejemplo  

 La página de codigos subyacente siguiente para el archivo XAML ejecuta una consulta asincrónica usando el servicio de datos y enlaza los resultados a los elementos de la ventana de WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Data Services de WCF](wcf-data-services-client-library.md)
