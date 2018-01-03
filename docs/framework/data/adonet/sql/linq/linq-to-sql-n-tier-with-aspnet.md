---
title: N niveles de LINQ to SQL con ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 477af694874ada4ae24fda0f1dbfac824a5aadbe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a><span data-ttu-id="5e640-102">N niveles de LINQ to SQL con ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5e640-102">LINQ to SQL N-Tier with ASP.NET</span></span>
<span data-ttu-id="5e640-103">En aplicaciones de [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] que usan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se utiliza el control de servidor web <xref:System.Web.UI.WebControls.LinqDataSource> .</span><span class="sxs-lookup"><span data-stu-id="5e640-103">In [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the <xref:System.Web.UI.WebControls.LinqDataSource> Web server control.</span></span> <span data-ttu-id="5e640-104">El control administra la mayor parte de la lógica necesaria para consultar contra [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pasar los datos al explorador, recuperarlos y enviarlos a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , que, a continuación, actualiza la base de datos.</span><span class="sxs-lookup"><span data-stu-id="5e640-104">The control handles most of the logic that it must have to query against [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pass the data to the browser, retrieve it, and submit it to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> which then updates the database.</span></span> <span data-ttu-id="5e640-105">El control, que se configura simplemente en el marcado, administra toda la transferencia de datos entre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y el explorador.</span><span class="sxs-lookup"><span data-stu-id="5e640-105">You just configure the control in the markup, and the control handles all the data transfer between [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] and the browser.</span></span> <span data-ttu-id="5e640-106">Puesto que el control administra las interacciones con el nivel de presentación, y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] administra la comunicación con la capa de datos, el trabajo principal en aplicaciones multinivel de [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] se centra en escribir la lógica empresarial personalizada.</span><span class="sxs-lookup"><span data-stu-id="5e640-106">Because the control handles the interactions with the presentation tier, and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] handles the communication with the data tier, your main focus in [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] multitier applications is on writing your custom business logic.</span></span>  
  
 <span data-ttu-id="5e640-107">Para obtener más información sobre `LINQDataSource`, consulte [Información general sobre el control de servidor web LinqDataSource](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).</span><span class="sxs-lookup"><span data-stu-id="5e640-107">For more information about `LINQDataSource`, see [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e640-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e640-108">See Also</span></span>  
 [<span data-ttu-id="5e640-109">Aplicaciones de n niveles y remotas con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5e640-109">N-Tier and Remote Applications with LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
