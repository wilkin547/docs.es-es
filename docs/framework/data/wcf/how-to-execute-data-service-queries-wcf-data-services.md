---
title: "Cómo: Ejecutar consultas de Data Services (Data Services de WCF)"
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
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: 62997821-e0c6-4c4d-9fb7-1273fb5e5d18
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ed40236fd902536a45e821abea768d5117fafde
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-execute-data-service-queries-wcf-data-services"></a>Cómo: Ejecutar consultas de Data Services (Data Services de WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite consultar un servicio datos desde una aplicación cliente basada en .NET Framework usando las clases generadas del servicio de datos del cliente. Puede ejecutar las consultas usando uno de estos métodos:  
  
-   Ejecutar una consulta LINQ en la instancia con nombre de <xref:System.Data.Services.Client.DataServiceQuery%601> que se obtiene desde la instancia de <xref:System.Data.Services.Client.DataServiceContext> generada por la herramienta `Add Data Service Reference`.  
  
-   Implícitamente, enumerando en la instancia con nombre de <xref:System.Data.Services.Client.DataServiceQuery%601> que se obtiene desde la instancia de <xref:System.Data.Services.Client.DataServiceContext> generada por la herramienta `Add Data Service Reference`.  
  
-   Explícitamente, llamando al método <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> de <xref:System.Data.Services.Client.DataServiceQuery%601> o al método <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> para la ejecución asincrónica.  
  
 Para obtener más información, consulte [consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Se crean este servicio y las clases de datos de cliente al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo definir y ejecutar en el servicio de datos de Northwind una consulta LINQ que devuelve todas las entidades `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getallcustomerslinq)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getallcustomerslinq)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo usar el contexto que genera la herramienta `Add Data Service Reference` para ejecutar implícitamente en el servicio de datos de Northwind una consulta que devuelve todas las entidades `Customers`. El contexto determina automáticamente el URI del conjunto de entidades `Customers` solicitado. La consulta se ejecuta implícitamente cuando se produce la enumeración.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getallcustomers)]
 [!code-vb[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getallcustomers)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar <xref:System.Data.Services.Client.DataServiceContext> para ejecutar explícitamente en el servicio de datos de Northwind una consulta que devuelve todas las entidades `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#getallcustomersexplicit)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#getallcustomersexplicit)]  
  
## <a name="see-also"></a>Vea también  
 [Adición de opciones de consulta a una consulta de servicio de datos](../../../../docs/framework/data/wcf/how-to-add-query-options-to-a-data-service-query-wcf-data-services.md)
