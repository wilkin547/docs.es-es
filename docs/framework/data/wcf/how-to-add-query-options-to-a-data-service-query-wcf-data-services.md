---
title: Procedimiento Agregar opciones de consulta a una consulta de servicio de datos (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- querying the data service [WCF Data Services]
- WCF Data Services, querying
- WCF Data Services, accessing data
ms.assetid: e4258526-557e-4e96-91e1-2175400c7c8f
ms.openlocfilehash: 2056b803b34faafdaebb85883de8b76ea2f9dcd8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59518063"
---
# <a name="how-to-add-query-options-to-a-data-service-query-wcf-data-services"></a>Procedimiento Agregar opciones de consulta a una consulta de servicio de datos (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] le permite consultar un servicio datos desde una aplicación cliente basada en .NET Framework usando las clases generadas del servicio de datos del cliente. La forma más fácil de hacerlo es crear una expresión de consulta Language Integrated Query (LINQ) que incluya las opciones de consulta deseadas. Además, puede llamar a una serie de métodos de consulta LINQ para crear una consulta equivalente. Por último, puede usar el método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> para agregar las opciones de consulta a una consulta. En cada uno de estos casos, el URI que genera el cliente incluye el conjunto de entidades solicitado con las opciones de consulta seleccionadas aplicadas. Para obtener más información, consulte [consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 En el ejemplo de este tema se usa el servicio de datos de ejemplo Northwind y las clases del servicio de datos de cliente generadas automáticamente. Este servicio y las clases de datos de cliente se crean cuando se completa la [inicio rápido de WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear una expresión de consulta LINQ que devuelve solo los pedidos con un coste de flete superior a 30 dólares y que ordena los resultados por la fecha de envío en orden descendente.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinq)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinq](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinq)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo crear un consulta LINQ, mediante los métodos de consulta LINQ, que es equivalente a la consulta anterior.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptionslinqexpression)]
 [!code-vb[Astoria Northwind Client#AddQueryOptionsLinqExpression](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptionslinqexpression)]  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo usar el método <xref:System.Data.Services.Client.DataServiceQuery%601.AddQueryOption%2A> para crear una clase <xref:System.Data.Services.Client.DataServiceQuery%601> que es equivalente a los ejemplos anteriores.  
  
 [!code-csharp[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addqueryoptions)]
 [!code-vb[Astoria Northwind Client#AddQueryOptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addqueryoptions)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar la opción de consulta `$orderby` para filtrar y ordenar los objetos Orders devueltos por la propiedad Freight.  
  
 [!code-csharp[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#orderwithfilter)]
 [!code-vb[Astoria Northwind Client#OrderWithFilter](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#orderwithfilter)]  
  
## <a name="see-also"></a>Vea también

- [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
- [Cómo: Resultados de la consulta](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md)
