---
title: Escribir un proveedor de datos de Entity Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a316ae288d677a0ad5bd602399e27389839ef092
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="3e550-102">Escribir un proveedor de datos de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="3e550-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="3e550-103">En esta sección se describe cómo escribir un proveedor de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] para admitir un origen de datos distinto de [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e550-103">This section discusses how to write an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider to support a data source other than [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3e550-104">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] incluye un proveedor que admite [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e550-104">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] includes a provider that supports [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="3e550-105">Introducción al modelo de proveedor de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="3e550-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="3e550-106">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] es independiente de la base de datos, por lo que puede escribir un proveedor utilizando el modelo de proveedor de ADO.NET para conectar a un conjunto diverso de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="3e550-106">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="3e550-107">El proveedor de datos de Entity Framework (compilado mediante el modelo de proveedor de datos de ADO.NET) realiza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="3e550-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
-   <span data-ttu-id="3e550-108">Asigna los tipos primitivos de Entity Data Model (EDM) a los tipos de proveedor.</span><span class="sxs-lookup"><span data-stu-id="3e550-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
-   <span data-ttu-id="3e550-109">Expone funciones específicas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="3e550-109">Exposes provider-specific functions.</span></span>  
  
-   <span data-ttu-id="3e550-110">Genera comandos específicos del proveedor para que un elemento DbQueryCommandTree determinado admita consultas de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e550-110">Generates provider-specific commands for a given DbQueryCommandTree to support [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] queries.</span></span>  
  
-   <span data-ttu-id="3e550-111">Genera comandos de actualización específicos del proveedor para que un elemento DbModificationCommandTree determinado admita las actualizaciones a través de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e550-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="3e550-112">Expone archivos de asignación para la definición de esquema de almacenamiento, para admitir la generación de un modelo basado en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="3e550-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
-   <span data-ttu-id="3e550-113">Expone metadatos (tablas y vistas, por ejemplo) a través de un modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="3e550-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="3e550-114">![b42a7a5c &#45; 0ac0 &#45; 4911 &#45; 86be &#45; 0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="3e550-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="3e550-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e550-115">Sample</span></span>  
 <span data-ttu-id="3e550-116">Consulte la [proveedor de ejemplo de Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) para obtener un ejemplo de un [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] proveedor que admite un origen de datos distinto a [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3e550-116">See the [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) for a sample of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider that supports a data source other than [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3e550-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3e550-117">In This Section</span></span>  
 [<span data-ttu-id="3e550-118">Generación de SQL</span><span class="sxs-lookup"><span data-stu-id="3e550-118">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [<span data-ttu-id="3e550-119">Generación de SQL de modificación</span><span class="sxs-lookup"><span data-stu-id="3e550-119">Modification SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [<span data-ttu-id="3e550-120">Especificación del manifiesto del proveedor</span><span class="sxs-lookup"><span data-stu-id="3e550-120">Provider Manifest Specification</span></span>](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="3e550-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e550-121">See Also</span></span>  
 [<span data-ttu-id="3e550-122">Trabajo con proveedores de datos</span><span class="sxs-lookup"><span data-stu-id="3e550-122">Working with Data Providers</span></span>](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
