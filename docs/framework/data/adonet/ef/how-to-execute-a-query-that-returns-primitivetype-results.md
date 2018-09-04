---
title: 'Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7139d585-4034-4dfa-916f-2120a8b72792
ms.openlocfilehash: 1e11e6c0e93710cad84ccd44ea9bffbd98080be1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511320"
---
# <a name="how-to-execute-a-query-that-returns-primitivetype-results"></a>Cómo: Ejecutar una consulta que devuelve resultados PrimitiveType
En este tema se muestra cómo ejecutar un comando en un modelo conceptual usando un objeto <xref:System.Data.EntityClient.EntityCommand>, y cómo recuperar los resultados de <xref:System.Data.Metadata.Edm.PrimitiveType> usando un objeto <xref:System.Data.EntityClient.EntityDataReader>.  
  
### <a name="to-run-the-code-in-this-example"></a>Para ejecutar el código de este ejemplo  
  
1.  Agregar el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) al proyecto y configurar el proyecto para usar el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se ejecuta una consulta que devuelve un resultado <xref:System.Data.Metadata.Edm.PrimitiveType>. Si pasa la siguiente consulta como un argumento a la función `ExecutePrimitiveTypeQuery`, la función muestra el precio de venta medio de todos los `Products`:  
  
 [!code-csharp[DP EntityServices Concepts 2#EDM_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#edm_avg)]  
  
 Si pasa una consulta parametrizada, como la siguiente, agregue los objetos <xref:System.Data.EntityClient.EntityParameter> a la propiedad <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> en el objeto <xref:System.Data.EntityClient.EntityCommand>.  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlprimitivetypes)]
 [!code-vb[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlprimitivetypes)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Proveedor de EntityClient para Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
