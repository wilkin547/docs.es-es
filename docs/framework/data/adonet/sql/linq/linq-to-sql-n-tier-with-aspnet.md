---
description: 'Más información acerca de: LINQ to SQL N niveles con ASP.NET'
title: N niveles de LINQ to SQL con ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: a455525f8f0bbef38487b058d89fd2c9b4dda377
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803807"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a><span data-ttu-id="d6c59-103">N niveles de LINQ to SQL con ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d6c59-103">LINQ to SQL N-Tier with ASP.NET</span></span>

<span data-ttu-id="d6c59-104">En las aplicaciones de ASP.NET que usan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , se utiliza el <xref:System.Web.UI.WebControls.LinqDataSource> control de servidor Web.</span><span class="sxs-lookup"><span data-stu-id="d6c59-104">In ASP.NET applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the <xref:System.Web.UI.WebControls.LinqDataSource> Web server control.</span></span> <span data-ttu-id="d6c59-105">El control administra la mayor parte de la lógica que debe tener para realizar consultas [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , pasar los datos al explorador, recuperarlos y enviarlos a la [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> , que actualiza la base de datos.</span><span class="sxs-lookup"><span data-stu-id="d6c59-105">The control handles most of the logic that it must have to query against [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pass the data to the browser, retrieve it, and submit it to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> which then updates the database.</span></span> <span data-ttu-id="d6c59-106">El control, que se configura simplemente en el marcado, administra toda la transferencia de datos entre [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] y el explorador.</span><span class="sxs-lookup"><span data-stu-id="d6c59-106">You just configure the control in the markup, and the control handles all the data transfer between [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] and the browser.</span></span> <span data-ttu-id="d6c59-107">Dado que el control administra las interacciones con el nivel de presentación y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] controla la comunicación con la capa de datos, el enfoque principal en las aplicaciones de varios niveles de ASP.net es escribir la lógica de negocios personalizada.</span><span class="sxs-lookup"><span data-stu-id="d6c59-107">Because the control handles the interactions with the presentation tier, and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] handles the communication with the data tier, your main focus in ASP.NET multitier applications is on writing your custom business logic.</span></span>  
  
 <span data-ttu-id="d6c59-108">Para obtener más información sobre `LINQDataSource` , vea [información general sobre el control de servidor Web LinqDataSource](/previous-versions/aspnet/bb547113(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d6c59-108">For more information about `LINQDataSource`, see [LinqDataSource Web Server Control Overview](/previous-versions/aspnet/bb547113(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c59-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6c59-109">See also</span></span>

- [<span data-ttu-id="d6c59-110">Aplicaciones de N niveles y remotas con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d6c59-110">N-Tier and Remote Applications with LINQ to SQL</span></span>](n-tier-and-remote-applications-with-linq-to-sql.md)
