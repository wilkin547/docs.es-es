---
title: "Cómo: Habilitar el acceso al servicio de datos (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, configuring
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f481a3a918282bf598277dcd4e1bf29d63edddc1
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-enable-access-to-the-data-service-wcf-data-services"></a><span data-ttu-id="1d264-102">Cómo: Habilitar el acceso al servicio de datos (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="1d264-102">How to: Enable Access to the Data Service (WCF Data Services)</span></span>
<span data-ttu-id="1d264-103">En [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], debe permitir explícitamente el acceso a los recursos expuestos por un servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="1d264-103">In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you must explicitly grant access to the resources that are exposed by a data service.</span></span> <span data-ttu-id="1d264-104">Esto significa que después de crear un nuevo servicio de datos, debe proporcionar explícitamente acceso a los recursos individuales como conjuntos de entidades.</span><span class="sxs-lookup"><span data-stu-id="1d264-104">This means that after you create a new data service, you must still explicitly provide access to individual resources as entity sets.</span></span> <span data-ttu-id="1d264-105">Este tema muestra cómo habilitar la lectura y acceso de escritura a cinco de la entidad se establece en el servicio de datos de Northwind que se crea cuando completa la [inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1d264-105">This topic shows how to enable read and write access to five of the entity sets in the Northwind data service that is created when you complete the [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="1d264-106">Dado que la enumeración <xref:System.Data.Services.EntitySetRights> se define utilizando <xref:System.FlagsAttribute>, puede utilizar un operador OR lógico para especificar varios permisos para un único conjunto de entidades.</span><span class="sxs-lookup"><span data-stu-id="1d264-106">Because the <xref:System.Data.Services.EntitySetRights> enumeration is defined by using the <xref:System.FlagsAttribute>, you can use a logical OR operator to specify multiple permissions for a single entity set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d264-107">Cualquier cliente que pueda tener acceso a la aplicación ASP.NET también puede tener acceso a los recursos expuestos por el servicio de datos.</span><span class="sxs-lookup"><span data-stu-id="1d264-107">Any client that can access the ASP.NET application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="1d264-108">En un servicio de datos de producción, para evitar el acceso no autorizado a los recursos, también debería proteger la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1d264-108">In a production data service, to prevent unauthorized access to resources, you should also secure the application itself.</span></span> <span data-ttu-id="1d264-109">Para obtener más información, consulte [NIB: seguridad de ASP.NET](http://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d).</span><span class="sxs-lookup"><span data-stu-id="1d264-109">For more information, see [NIB: ASP.NET Security](http://msdn.microsoft.com/library/04b37532-18d9-40b4-8e5f-ee09a70b311d).</span></span>  
  
### <a name="to-enable-access-to-the-data-service"></a><span data-ttu-id="1d264-110">Para habilitar el acceso al servicio de datos</span><span class="sxs-lookup"><span data-stu-id="1d264-110">To enable access to the data service</span></span>  
  
-   <span data-ttu-id="1d264-111">En el código del servicio de datos, reemplace el código de marcador de posición de la función `InitializeService` por el siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d264-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="1d264-112">De esta forma, los clientes pueden tener acceso de lectura y escritura a los conjuntos de entidades de `Orders` y `Order_Details`, y acceso de solo lectura a los conjuntos de entidades de `Customers`.</span><span class="sxs-lookup"><span data-stu-id="1d264-112">This enables clients to have read and write access to the `Orders` and `Order_Details` entity sets and read-only access to the `Customers` entity sets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d264-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d264-113">See Also</span></span>  
 [<span data-ttu-id="1d264-114">Desarrollo de un servicio de datos WCF que se ejecuta en IIS</span><span class="sxs-lookup"><span data-stu-id="1d264-114">How to: Develop a WCF Data Service Running on IIS</span></span>](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)  
 [<span data-ttu-id="1d264-115">Configuración del servicio de datos</span><span class="sxs-lookup"><span data-stu-id="1d264-115">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
