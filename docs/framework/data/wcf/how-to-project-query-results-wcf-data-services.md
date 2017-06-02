---
title: "C&#243;mo: Proyectar los resultados de una consulta (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "proyección [WCF Data Services]"
  - "proyección de consultas [WCF Data Services]"
  - "Servicios de datos de Microsoft WCF, proyección"
  - "Servicios de datos de Microsoft WCF, consultar"
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# C&#243;mo: Proyectar los resultados de una consulta (WCF Data Services)
La proyección proporciona un mecanismo para reducir la cantidad de datos devueltos por una consulta mediante la especificación de que solo se devuelven algunas propiedades de una entidad en la respuesta.  Puede realizar proyecciones en los resultados de una consulta de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] mediante la opción de consulta `$select` o mediante la cláusula [select](../Topic/select%20clause%20\(C%23%20Reference\).md) \([Select](../Topic/Select%20Clause%20\(Visual%20Basic\).md) en Visual Basic\) en una consulta LINQ.  Para obtener más información, consulte [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente.  Se crean este servicio y las clases de datos del cliente al completar el [tutorial rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Ejemplo  
 En el siguiente ejemplo se muestra una consulta LINQ que proyecta entidades Customers en un nuevo tipo CustomerAddress, que solo contiene las propiedades específicas de la dirección más la propiedad de identidad.  Esta clase `CustomerAddress` se define en el cliente y recibe el atributo para que la biblioteca de cliente pueda reconocerla como tipo de entidad.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddress)]  
  
## Ejemplo  
 En el siguiente ejemplo se muestra una consulta LINQ que proyecta las entidades Customers devueltas en un nuevo tipo CustomerAddressNonEntity, que solo contiene las propiedades específicas de la dirección y no tiene propiedad de identidad.  Esta clase `CustomerAddressNonEntity` se define en el cliente y no recibe el atributo como tipo de entidad.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## Ejemplo  
 En el siguiente ejemplo se muestran las definiciones de los tipos `CustomerAddress` `CustomerAddressNonEntity` usados en los ejemplos anteriores.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customeraddress.vb#customeraddressdefinition)]