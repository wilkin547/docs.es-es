---
title: "Cómo: Ejecutar consultas asincrónicas de Data Services (Data Services de WCF)"
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
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 86c38049f21ff6e9e02e1e715e6517c2947394e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Cómo: Ejecutar consultas asincrónicas de Data Services (Data Services de WCF)
Al usar la biblioteca de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], puede realizar operaciones cliente-servidor, como ejecutar consultas y guardar cambios, de forma asincrónica. Para obtener más información, consulte [operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
>  En una aplicación donde se debe invocar la devolución de llamada en un subproceso concreto, debe calcular explícitamente las referencias de la ejecución del método <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>. Para obtener más información, consulte [operaciones asincrónicas](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Se crean este servicio y las clases de datos de cliente al completar la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo ejecutar una consulta asincrónica llamando al método <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> para iniciar la consulta. El delegado alineado llama al método <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> para mostrar los resultados de la consulta.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
