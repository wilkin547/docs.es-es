---
title: 'Cómo: Habilitar el acceso al servicio de datos (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: eb9d7cd8e62a73f49fd2b0f2fc2572b01109553b
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44214841"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="52bd4-102">Cómo: Habilitar el acceso al servicio de datos (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="52bd4-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="52bd4-103">En [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], debe permitir explícitamente el acceso a los recursos expuestos por un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="52bd4-103">In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="52bd4-104">Esto significa que después de crear un nuevo servicio de datos, debe proporcionar explícitamente acceso a los recursos individuales como conjuntos de entidades.</span><span class="sxs-lookup"><span data-stu-id="52bd4-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="52bd4-105">En este tema se muestra cómo habilitar la lectura y acceso de escritura a cinco de la entidad se establece en el servicio de datos de Northwind que se crea cuando se completa la [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="52bd4-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="52bd4-106">Dado que la enumeración <xref:System.Data.Services.EntitySetRights> se define utilizando <xref:System.FlagsAttribute>, puede utilizar un operador OR lógico para especificar varios permisos para un único conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="52bd4-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52bd4-107">Cualquier cliente que pueda tener acceso a la aplicación ASP.NET también puede tener acceso a los recursos expuestos por el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="52bd4-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="52bd4-108">En un servicio de datos de producción, para evitar el acceso no autorizado a los recursos, también debería proteger la aplicación.</span><span class="sxs-lookup"><span data-stu-id="52bd4-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="52bd4-109">Para obtener más información, consulte [NIB: seguridad de ASP.NET](https://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d).</span><span class="sxs-lookup"><span data-stu-id="52bd4-109">For more information, see [NIB: ASP.NET Security](https://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="52bd4-110">Para habilitar el acceso al servicio de datos</span><span class="sxs-lookup"><span data-stu-id="52bd4-110">To enable access to the data service</span></span>  
  
-   <span data-ttu-id="52bd4-111">En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="52bd4-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="52bd4-112">De esta forma, los clientes pueden tener acceso de lectura y escritura a los conjuntos de entidades de `Orders` y `Order_Details`, y acceso de solo lectura a los conjuntos de entidades de `Customers`.</span><span class="sxs-lookup"><span data-stu-id="52bd4-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52bd4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="52bd4-113">See Also</span></span>  
 [<span data-ttu-id="52bd4-114">Desarrollo de un servicio de datos WCF que se ejecuta en IIS</span><span class="sxs-lookup"><span data-stu-id="52bd4-114">How to: Develop a WCF Data Service Running on IIS</span></span>](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)  
 [<span data-ttu-id="52bd4-115">Configuración del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="52bd4-115">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
