---
title: Aplicaciones de n niveles y remotas con LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 004e64584027d40368592097c76ad0830e942f07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a><span data-ttu-id="53128-102">Aplicaciones de n niveles y remotas con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="53128-102">N-Tier and Remote Applications with LINQ to SQL</span></span>
<span data-ttu-id="53128-103">Puede crear aplicaciones multinivel o de n niveles que utilicen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53128-103">You can create n-tier or multitier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="53128-104">Normalmente, el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] lógica de construcción de consulta, contexto de datos y las clases de entidad que se encuentran en el nivel intermedio como la capa de acceso a datos (DAL).</span><span class="sxs-lookup"><span data-stu-id="53128-104">Typically, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] data context, entity classes, and query construction logic are located on the middle tier as the data access layer (DAL).</span></span> <span data-ttu-id="53128-105">La lógica empresarial y los datos no persistentes se pueden implementar completamente en clases parciales y métodos de entidades y en el contexto de los datos, o se pueden implementar en clases independientes.</span><span class="sxs-lookup"><span data-stu-id="53128-105">Business logic and any non-persistent data can be implemented completely in partial classes and methods of entities and the data context, or it can be implemented in separate classes.</span></span>  
  
 <span data-ttu-id="53128-106">La capa de presentación o de cliente llama a los métodos en la interfaz remota de nivel intermedio, y la capa de acceso a datos (DAL) en ese nivel ejecutará consultas o procedimientos almacenados asignados a métodos <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="53128-106">The client or presentation layer calls methods on the middle-tier's remote interface, and the DAL on that tier will execute queries or stored procedures that are mapped to <xref:System.Data.Linq.DataContext> methods.</span></span> <span data-ttu-id="53128-107">El nivel intermedio devuelve los datos a los clientes generalmente como representaciones XML de entidades u objetos proxy.</span><span class="sxs-lookup"><span data-stu-id="53128-107">The middle tier returns the data to clients typically as XML representations of entities or proxy objects.</span></span>  
  
 <span data-ttu-id="53128-108">En el nivel intermedio, las entidades son creadas por el contexto de los datos, el cual realiza el seguimiento de su estado, y administra la carga aplazada desde, y el envío de los cambios a, la base de datos.</span><span class="sxs-lookup"><span data-stu-id="53128-108">On the middle tier, entities are created by the data context, which tracks their state, and manages deferred loading from and submission of changes to the database.</span></span> <span data-ttu-id="53128-109">Estas entidades están "asociadas" al `DataContext`.</span><span class="sxs-lookup"><span data-stu-id="53128-109">These entities are "attached" to the `DataContext`.</span></span> <span data-ttu-id="53128-110">Sin embargo, una vez que las entidades se han enviado a otro nivel a través de la serialización, quedan desasociadas, lo cual significa que el `DataContext` ya no realiza el seguimiento de su estado.</span><span class="sxs-lookup"><span data-stu-id="53128-110">However, after the entities are sent to another tier through serialization, they become detached, which means the `DataContext` is no longer tracking their state.</span></span> <span data-ttu-id="53128-111">Las entidades que el cliente devuelve para las actualizaciones se deben volver a asociar al contexto de los datos antes de que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] pueda enviar los cambios a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="53128-111">Entities that the client sends back for updates must be reattached to the data context before [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can submit the changes to the database.</span></span> <span data-ttu-id="53128-112">El cliente es responsable de devolver valores originales y/o marcas de tiempo al nivel intermedio si se requieren para las comprobaciones de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="53128-112">The client is responsible for providing original values and/or timestamps back to the middle tier if those are required for optimistic concurrency checks.</span></span>  
  
 <span data-ttu-id="53128-113">En aplicaciones ASP.NET, <xref:System.Web.UI.WebControls.LinqDataSource> administra la mayor parte de esta complejidad.</span><span class="sxs-lookup"><span data-stu-id="53128-113">In ASP.NET applications, the <xref:System.Web.UI.WebControls.LinqDataSource> manages most of this complexity.</span></span> <span data-ttu-id="53128-114">Para obtener más información, consulte [NIB: información general sobre el Control de servidor Web LinqDataSource](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).</span><span class="sxs-lookup"><span data-stu-id="53128-114">For more information, see [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="53128-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="53128-115">Additional Resources</span></span>  
 <span data-ttu-id="53128-116">Para obtener más información sobre cómo implementar aplicaciones de n niveles que utilizan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="53128-116">For more information about how to implement n-tier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], see the following topics:</span></span>  
  
-   [<span data-ttu-id="53128-117">N niveles de LINQ to SQL con ASP.NET</span><span class="sxs-lookup"><span data-stu-id="53128-117">LINQ to SQL N-Tier with ASP.NET</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [<span data-ttu-id="53128-118">N niveles de LINQ to SQL con servicios web</span><span class="sxs-lookup"><span data-stu-id="53128-118">LINQ to SQL N-Tier with Web Services</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [<span data-ttu-id="53128-119">LINQ to SQL con aplicaciones cliente/servidor estrechamente asociadas</span><span class="sxs-lookup"><span data-stu-id="53128-119">LINQ to SQL with Tightly-Coupled Client-Server Applications</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [<span data-ttu-id="53128-120">Implementación de una lógica de negocios de n niveles</span><span class="sxs-lookup"><span data-stu-id="53128-120">Implementing N-Tier Business Logic</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [<span data-ttu-id="53128-121">Recuperación de datos y operaciones CUD en aplicaciones de n niveles (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="53128-121">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 <span data-ttu-id="53128-122">Para obtener más información acerca de las aplicaciones de n niveles que utilizan conjuntos de datos ADO.NET, vea [trabajar con conjuntos de datos en aplicaciones de n niveles](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).</span><span class="sxs-lookup"><span data-stu-id="53128-122">For more information about n-tier applications that use ADO.NET DataSets, see [Work with datasets in n-tier applications](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53128-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="53128-123">See Also</span></span>  
 [<span data-ttu-id="53128-124">Información general</span><span class="sxs-lookup"><span data-stu-id="53128-124">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
