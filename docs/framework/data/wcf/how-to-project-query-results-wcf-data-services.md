---
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
ms.openlocfilehash: 8a3a278a8459da073b7ad3cbf8d1fff1d435a18c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175192"
---
# <a name="how-to-project-query-results-wcf-data-services"></a>Cómo: Proyectar los resultados de la consulta (Data Services de WCF)

La proyección proporciona un mecanismo para reducir la cantidad de datos devueltos por una consulta mediante la especificación de que solo se devuelven algunas propiedades de una entidad en la respuesta. Puede realizar proyecciones en los resultados de una consulta de WCF Data Services mediante la `$select` opción de consulta o mediante la cláusula [Select](../../../csharp/language-reference/keywords/select-clause.md) ([Select](../../../visual-basic/language-reference/queries/select-clause.md) en Visual Basic) en una consulta LINQ. Para obtener más información, consulte [consultar el servicio de datos](querying-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean al completar la guía de [Inicio rápido de WCF Data Services](quickstart-wcf-data-services.md).  
  
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
