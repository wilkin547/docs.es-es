---
title: Procedimiento para navegar por las relaciones con el operador Navigate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: c8c23e00112859ffa9949d268c3263f73d3a714f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251430"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a>Procedimiento para navegar por las relaciones con el operador Navigate
En este tema se muestra cómo ejecutar un comando contra un modelo conceptual usando un objeto <xref:System.Data.EntityClient.EntityCommand>, y cómo recuperar los resultados de <xref:System.Data.Metadata.Edm.RefType> usando un <xref:System.Data.EntityClient.EntityDataReader>.  
  
### <a name="to-run-the-code-in-this-example"></a>Para ejecutar el código de este ejemplo  
  
1. Agregue el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configure el proyecto para que use [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]el. Para obtener más información, consulte [Cómo Use el Asistente para](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.  
  
2. En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo navegar por [!INCLUDE[esql](../../../../../includes/esql-md.md)] las relaciones de mediante el operador [Navigate](./language-reference/navigate-entity-sql.md) . El `Navigate` operador acepta los parámetros siguientes: una instancia de una entidad, el tipo de relación, el extremo de la relación y el comienzo de la relación. Opcionalmente, solo puede pasar una instancia de una entidad y el tipo de relación al `Navigate` operador.  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a>Vea también

- [Proveedor de EntityClient para Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Lenguaje Entity SQL](./language-reference/entity-sql-language.md)
