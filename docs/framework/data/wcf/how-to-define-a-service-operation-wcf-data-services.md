---
description: 'Más información acerca de cómo: definir una operación de servicio (Servicios de datos de WCF)'
title: 'Cómo: Definir una operación de servicio (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: 9fcad3a31ea5b439c248ba103cbf4ddd75b8109a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765625"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a>Cómo: Definir una operación de servicio (Data Services de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Servicios de datos de WCF exponer métodos que se definen en el servidor como operaciones de servicio. Las operaciones de servicio permiten que un servicio de datos proporcione acceso a través de un URI a un método que se define en el servidor. Para definir una operación de servicio, aplique el `WebGet]` atributo [o `[WebInvoke]` al método. Para admitir los operadores de consulta, la operación de servicio debe devolver una <xref:System.Linq.IQueryable%601> instancia de. Las operaciones del servicio pueden tener acceso al origen de datos subyacente por medio de la propiedad <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> en <xref:System.Data.Services.DataService%601>. Para obtener más información, consulte [operaciones de servicio](service-operations-wcf-data-services.md).

En el ejemplo de este tema se define una operación del servicio denominada `GetOrdersByCity` que devuelve una instancia de <xref:System.Linq.IQueryable%601> filtrada de los objetos `Orders` y `Order_Details` relacionados. En el ejemplo se obtiene acceso a la instancia de <xref:System.Data.Objects.ObjectContext> que es el origen de datos del servicio de datos de ejemplo Northwind. Este servicio se crea cuando se completa la guía de [Inicio rápido de servicios de datos de WCF](quickstart-wcf-data-services.md).

### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a>Para definir una operación del servicio en el servicio de datos Northwind

1. En el proyecto del servicio de datos Northwind, abra el archivo Northwind.svc.

2. En la clase `Northwind`, defina un método de operación de servicio denominado `GetOrdersByCity` como sigue:

     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationdef)]

3. En el método `InitializeService` de la clase `Northwind`, agregue el siguiente código para permitir el acceso a la operación del servicio:

     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationconfig)]

### <a name="to-query-the-getordersbycity-service-operation"></a>Para consultar la operación del servicio GetOrdersByCity

- En un explorador web, escriba uno de los siguientes URI para invocar la operación del servicio que se define en el siguiente ejemplo:

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se implementa una operación del servicio denominada `GetOrderByCity` en el servicio de datos Northwind. Esta operación utiliza ADO.NET Entity Framework para devolver un conjunto de objetos `Orders` y `Order_Details` relacionados como una instancia de <xref:System.Linq.IQueryable%601> basada en el nombre de ciudad suministrado.

> [!NOTE]
> Los operadores de consulta se admiten en este extremo de la operación del servicio porque el método devuelve una instancia de <xref:System.Linq.IQueryable%601>.

[!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperation)]
[!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperation)]

## <a name="see-also"></a>Vea también

- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
