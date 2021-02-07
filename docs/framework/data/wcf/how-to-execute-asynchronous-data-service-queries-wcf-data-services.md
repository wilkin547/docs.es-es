---
description: 'Más información acerca de cómo: ejecutar consultas asincrónicas de servicios de datos (Servicios de datos de WCF)'
title: 'Cómo: Ejecutar consultas asincrónicas de Data Services (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
- asynchronous operations [WCF Data Services]
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
ms.openlocfilehash: 35300de319673b29484dc981b5d6d51c964ad908
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765352"
---
# <a name="how-to-execute-asynchronous-data-service-queries-wcf-data-services"></a>Cómo: Ejecutar consultas asincrónicas de Data Services (Data Services de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Mediante el uso de la biblioteca de cliente de Servicios de datos de WCF, puede realizar de forma asincrónica operaciones cliente-servidor, como ejecutar consultas y guardar cambios. Para obtener más información, vea [operaciones asincrónicas](asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
> En una aplicación donde se debe invocar la devolución de llamada en un subproceso concreto, debe calcular explícitamente las referencias de la ejecución del método <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>. Para obtener más información, vea [operaciones asincrónicas](asynchronous-operations-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de servicios de datos de WCF](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se muestra cómo ejecutar una consulta asincrónica llamando al método <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> para iniciar la consulta. El delegado alineado llama al método <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> para mostrar los resultados de la consulta.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#executequeryasync)]  
  
## <a name="see-also"></a>Vea también

- [Biblioteca cliente de Data Services de WCF](wcf-data-services-client-library.md)
