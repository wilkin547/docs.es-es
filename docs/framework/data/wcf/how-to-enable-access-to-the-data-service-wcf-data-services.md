---
title: 'Cómo: Habilitar el acceso al servicio de datos (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
ms.openlocfilehash: 62622a5788a735497a6869c114c572e947067449
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155424"
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="b791d-102">Cómo: Habilitar el acceso al servicio de datos (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="b791d-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>

<span data-ttu-id="b791d-103">En WCF Data Services, debe conceder explícitamente acceso a los recursos expuestos por un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="b791d-103">In WCF Data Services, you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="b791d-104">Esto significa que después de crear un nuevo servicio de datos, debe proporcionar explícitamente acceso a los recursos individuales como conjuntos de entidades.</span><span class="sxs-lookup"><span data-stu-id="b791d-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="b791d-105">En este tema se muestra cómo habilitar el acceso de lectura y escritura a cinco de los conjuntos de entidades del servicio de datos de Northwind que se crea al completar la guía de [Inicio rápido](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="b791d-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="b791d-106">Dado que la enumeración <xref:System.Data.Services.EntitySetRights> se define utilizando <xref:System.FlagsAttribute>, puede utilizar un operador OR lógico para especificar varios permisos para un único conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="b791d-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b791d-107">Cualquier cliente que pueda tener acceso a la aplicación ASP.NET también puede tener acceso a los recursos expuestos por el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="b791d-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="b791d-108">En un servicio de datos de producción, para evitar el acceso no autorizado a los recursos, también debería proteger la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b791d-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="b791d-109">Para obtener más información, consulte [protección de sitios web de ASP.net](/previous-versions/aspnet/91f66yxt(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b791d-109">For more information, see [Securing ASP.NET Web Sites](/previous-versions/aspnet/91f66yxt(v=vs.100)).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="b791d-110">Para habilitar el acceso al servicio de datos</span><span class="sxs-lookup"><span data-stu-id="b791d-110">To enable access to the data service</span></span>  
  
- <span data-ttu-id="b791d-111">En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="b791d-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="b791d-112">De esta forma, los clientes pueden tener acceso de lectura y escritura a los conjuntos de entidades de `Orders` y `Order_Details`, y acceso de solo lectura a los conjuntos de entidades de `Customers`.</span><span class="sxs-lookup"><span data-stu-id="b791d-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b791d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b791d-113">See also</span></span>

- [<span data-ttu-id="b791d-114">Procedimiento para desarrollar un servicio de datos WCF que se ejecuta en IIS</span><span class="sxs-lookup"><span data-stu-id="b791d-114">How to: Develop a WCF Data Service Running on IIS</span></span>](how-to-develop-a-wcf-data-service-running-on-iis.md)
- [<span data-ttu-id="b791d-115">Configuración del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="b791d-115">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)
