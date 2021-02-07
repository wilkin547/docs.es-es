---
description: 'Más información acerca de cómo: proyectar los resultados de una consulta (Servicios de datos de WCF)'
title: 'Cómo: Proyectar los resultados de la consulta (Data Services de WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
ms.openlocfilehash: a851176e5f97e31d2e8d9ac62c720d04df4ddc37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765118"
---
# <a name="how-to-project-query-results-wcf-data-services"></a>Cómo: Proyectar los resultados de la consulta (Data Services de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

La proyección proporciona un mecanismo para reducir la cantidad de datos devueltos por una consulta mediante la especificación de que solo se devuelven algunas propiedades de una entidad en la respuesta. Puede realizar proyecciones en los resultados de una consulta de Servicios de datos de WCF mediante la `$select` opción de consulta o mediante la cláusula [Select](../../../csharp/language-reference/keywords/select-clause.md) ([Select](../../../visual-basic/language-reference/queries/select-clause.md) en Visual Basic) en una consulta LINQ. Para obtener más información, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de servicios de datos de WCF](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se muestra una consulta LINQ que proyecta entidades Customers en un nuevo tipo CustomerAddress, que solo contiene las propiedades específicas de la dirección más la propiedad de identidad. Esta clase `CustomerAddress` se define en el cliente y recibe el atributo para que la biblioteca de cliente pueda reconocerla como tipo de entidad.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddress)]  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se muestra una consulta LINQ que proyecta las entidades Customers devueltas en un nuevo tipo CustomerAddressNonEntity, que solo contiene las propiedades específicas de la dirección y no tiene propiedad de identidad. Esta clase `CustomerAddressNonEntity` se define en el cliente y no recibe el atributo como tipo de entidad.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestran las definiciones de los `CustomerAddress` `CustomerAddressNonEntity` tipos y que se usan en los ejemplos anteriores.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customeraddress.vb#customeraddressdefinition)]
