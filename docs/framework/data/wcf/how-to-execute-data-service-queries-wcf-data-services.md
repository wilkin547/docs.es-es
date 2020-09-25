---
title: 'Cómo: Ejecutar consultas de Data Services (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: 62997821-e0c6-4c4d-9fb7-1273fb5e5d18
ms.openlocfilehash: 11a37340df879db7c2f8fdeaa792c1466e4a75d0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184760"
---
# <a name="how-to-execute-data-service-queries-wcf-data-services"></a>Cómo: Ejecutar consultas de Data Services (Data Services de WCF)

WCF Data Services permite consultar un servicio de datos desde una aplicación cliente basada en .NET Framework mediante las clases de servicio de datos del cliente generadas. Puede ejecutar las consultas usando uno de estos métodos:  
  
- Ejecutar una consulta LINQ en la instancia con nombre de <xref:System.Data.Services.Client.DataServiceQuery%601> que se obtiene desde la instancia de <xref:System.Data.Services.Client.DataServiceContext> generada por la herramienta `Add Data Service Reference`.  
  
- Implícitamente, enumerando en la instancia con nombre de <xref:System.Data.Services.Client.DataServiceQuery%601> que se obtiene desde la instancia de <xref:System.Data.Services.Client.DataServiceContext> generada por la herramienta `Add Data Service Reference`.  
  
- Explícitamente, llamando al método <xref:System.Data.Services.Client.DataServiceContext.Execute%2A> de <xref:System.Data.Services.Client.DataServiceQuery%601> o al método <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> para la ejecución asincrónica.  
  
 Para obtener más información, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo definir y ejecutar en el servicio de datos de Northwind una consulta LINQ que devuelve todas las entidades `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomerslinq)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomerslinq)]  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se muestra cómo usar el contexto que genera la herramienta `Add Data Service Reference` para ejecutar implícitamente en el servicio de datos de Northwind una consulta que devuelve todas las entidades `Customers`. El contexto determina automáticamente el URI del conjunto de entidades `Customers` solicitado. La consulta se ejecuta implícitamente cuando se produce la enumeración.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomers)]
 [!code-vb[Astoria Northwind Client#GetAllCustomers](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomers)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo usar <xref:System.Data.Services.Client.DataServiceContext> para ejecutar explícitamente en el servicio de datos de Northwind una consulta que devuelve todas las entidades `Customers`.  
  
 [!code-csharp[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#getallcustomersexplicit)]
 [!code-vb[Astoria Northwind Client#GetAllCustomersExplicit](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#getallcustomersexplicit)]  
  
## <a name="see-also"></a>Consulte también

- [Procedimiento para agregar opciones de consulta a una consulta de servicio de datos](how-to-add-query-options-to-a-data-service-query-wcf-data-services.md)
