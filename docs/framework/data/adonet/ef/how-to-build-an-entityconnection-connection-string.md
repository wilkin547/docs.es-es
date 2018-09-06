---
title: 'Cómo: Compilar una cadena de conexión EntityConnection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: a35a0bf54d7850e4b10e59c259e4ee512bc93aad
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43744525"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a><span data-ttu-id="a4486-102">Cómo: Compilar una cadena de conexión EntityConnection</span><span class="sxs-lookup"><span data-stu-id="a4486-102">How to: Build an EntityConnection Connection String</span></span>
<span data-ttu-id="a4486-103">En este tema se muestra un ejemplo para generar una <xref:System.Data.EntityClient.EntityConnection>.</span><span class="sxs-lookup"><span data-stu-id="a4486-103">This topic provides an example of how to build an <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="a4486-104">Para ejecutar el código de este ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4486-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="a4486-105">Agregar el [modelo AdventureWorks Sales](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) al proyecto y configurar el proyecto para usar el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4486-105">Add the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="a4486-106">Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="a4486-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="a4486-107">En la página de código de la aplicación, agregue las instrucciones `using` siguientes (`Imports` en Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="a4486-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="a4486-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4486-108">Example</span></span>  
 <span data-ttu-id="a4486-109">En el siguiente ejemplo se inicializa el <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> para el proveedor subyacente y, a continuación, se inicializa el objeto <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> y se pasa este objeto al constructor de <xref:System.Data.EntityClient.EntityConnection>.</span><span class="sxs-lookup"><span data-stu-id="a4486-109">The following example initializes the <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> for the underlying provider, then initializes the <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> object and passes this object to the constructor of the <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="a4486-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4486-110">See Also</span></span>  
 [<span data-ttu-id="a4486-111">Cómo: usar EntityConnection con un contexto del objeto</span><span class="sxs-lookup"><span data-stu-id="a4486-111">How to: Use EntityConnection with an Object Context</span></span>](https://msdn.microsoft.com/library/2140fe7b-b88b-47c8-a749-d7f142eb1080)  
 [<span data-ttu-id="a4486-112">Proveedor de EntityClient para Entity Framework</span><span class="sxs-lookup"><span data-stu-id="a4486-112">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
