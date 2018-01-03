---
title: "Cómo: Interceptar mensajes de Data Services (Data Services de WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 28f69bb7f584c8d9e7031d969dce0052b1541aad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a>Cómo: Interceptar mensajes de Data Services (Data Services de WCF)
Con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede interceptar mensajes de solicitud, lo que le permitirá agregar lógica personalizada a una operación. Para interceptar un mensaje, se utilizan métodos con atributos especiales en el servicio de datos. Para obtener más información, consulte [interceptores](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind. Este servicio se crea al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a>Para definir un interceptor de consultas para el conjunto de entidades Orders  
  
1.  En el proyecto del servicio de datos Northwind, abra el archivo Northwind.svc.  
  
2.  En la página de codigos de la clase `Northwind`, agregue la instrucción `using` siguiente (`Imports` en Visual Basic).  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3.  En la clase `Northwind`, defina un método de operación de servicio denominado `OnQueryOrders` como sigue:  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a>Para definir un interceptor de cambios para el conjunto de entidades Products  
  
1.  En el proyecto del servicio de datos Northwind, abra el archivo Northwind.svc.  
  
2.  En la clase `Northwind`, defina un método de operación de servicio denominado `OnChangeProducts` como sigue:  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se define un método de interceptor de consultas para el conjunto de entidades `Orders` que devuelve una expresión lambda. Esta expresión contiene un delegado que filtra los pedidos (`Orders`) solicitados basándose en los clientes (`Customers`) relacionados que tienen un nombre de contacto concreto. El nombre se determina a su vez en función del usuario que realiza la solicitud. En este ejemplo se supone que el servicio de datos se hospeda dentro de una aplicación web ASP.NET que usa WCF, y que la autenticación está habilitada. La clase <xref:System.Web.HttpContext> se usa para recuperar el principio de la solicitud actual.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se define un método interceptor de cambios para el conjunto de entidades `Products`. Este método valida la entrada al servicio para una operación <xref:System.Data.Services.UpdateOperations.Add> o <xref:System.Data.Services.UpdateOperations.Change> y produce una excepción si se hace un cambio en un producto que ya no se fabrica. También bloquea la eliminación de productos como una operación no admitida.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a>Vea también  
 [Definición de una operación de servicio](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)  
 [Definir Servicios de datos de WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
