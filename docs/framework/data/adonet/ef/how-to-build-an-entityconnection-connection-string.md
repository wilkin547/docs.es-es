---
title: Procedimiento para compilar una cadena de conexión EntityConnection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: 33a52b2542a2e312f7fbb8b7ca09a8b85662d2d4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251548"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a><span data-ttu-id="f26d8-102">Procedimiento para compilar una cadena de conexión EntityConnection</span><span class="sxs-lookup"><span data-stu-id="f26d8-102">How to: Build an EntityConnection Connection String</span></span>
<span data-ttu-id="f26d8-103">En este tema se muestra un ejemplo para generar una <xref:System.Data.EntityClient.EntityConnection>.</span><span class="sxs-lookup"><span data-stu-id="f26d8-103">This topic provides an example of how to build an <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="f26d8-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="f26d8-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="f26d8-105">Agregue el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) al proyecto y configure el proyecto para que use [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]el.</span><span class="sxs-lookup"><span data-stu-id="f26d8-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="f26d8-106">Para obtener más información, vea [Cómo: Use el Asistente para](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="f26d8-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="f26d8-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="f26d8-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="f26d8-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f26d8-108">Example</span></span>  
 <span data-ttu-id="f26d8-109">En el siguiente ejemplo se inicializa el <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> para el proveedor subyacente y, a continuación, se inicializa el objeto <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> y se pasa este objeto al constructor de <xref:System.Data.EntityClient.EntityConnection>.</span><span class="sxs-lookup"><span data-stu-id="f26d8-109">The following example initializes the <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> for the underlying provider, then initializes the <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> object and passes this object to the constructor of the <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="f26d8-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f26d8-110">See also</span></span>

- <span data-ttu-id="f26d8-111">[Cómo: Usar EntityConnection con un contexto del objeto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f26d8-111">[How to: Use EntityConnection with an Object Context](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span></span>
- [<span data-ttu-id="f26d8-112">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="f26d8-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
