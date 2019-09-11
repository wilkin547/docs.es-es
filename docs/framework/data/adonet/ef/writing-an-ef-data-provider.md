---
title: Escribir un proveedor de datos de Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854163"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="43b78-102">Escribir un proveedor de datos de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="43b78-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="43b78-103">En esta sección se explica cómo escribir un proveedor de Entity Framework para admitir un origen de datos que no sea SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43b78-103">This section discusses how to write an Entity Framework provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="43b78-104">El Entity Framework incluye un proveedor que admite SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43b78-104">The Entity Framework includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="43b78-105">Introducción al modelo de proveedor de Entity Framework</span><span class="sxs-lookup"><span data-stu-id="43b78-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="43b78-106">El Entity Framework es independiente de la base de datos y puede escribir un proveedor mediante el modelo de proveedor ADO.NET para conectarse a un conjunto diverso de orígenes de datos.</span><span class="sxs-lookup"><span data-stu-id="43b78-106">The Entity Framework is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="43b78-107">El proveedor de datos de Entity Framework (compilado mediante el modelo de proveedor de datos de ADO.NET) realiza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="43b78-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
- <span data-ttu-id="43b78-108">Asigna los tipos primitivos de Entity Data Model (EDM) a los tipos de proveedor.</span><span class="sxs-lookup"><span data-stu-id="43b78-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
- <span data-ttu-id="43b78-109">Expone funciones específicas del proveedor.</span><span class="sxs-lookup"><span data-stu-id="43b78-109">Exposes provider-specific functions.</span></span>  
  
- <span data-ttu-id="43b78-110">Genera comandos específicos del proveedor para que un DbQueryCommandTree determinado admita consultas Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="43b78-110">Generates provider-specific commands for a given DbQueryCommandTree to support Entity Framework queries.</span></span>  
  
- <span data-ttu-id="43b78-111">Genera comandos de actualización específicos del proveedor para que un DbModificationCommandTree determinado admita actualizaciones a través de la Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="43b78-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the Entity Framework.</span></span>  
  
- <span data-ttu-id="43b78-112">Expone archivos de asignación para la definición de esquema de almacenamiento, para admitir la generación de un modelo basado en una base de datos.</span><span class="sxs-lookup"><span data-stu-id="43b78-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
- <span data-ttu-id="43b78-113">Expone metadatos (tablas y vistas, por ejemplo) a través de un modelo conceptual.</span><span class="sxs-lookup"><span data-stu-id="43b78-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="43b78-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="43b78-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="43b78-115">Muestra</span><span class="sxs-lookup"><span data-stu-id="43b78-115">Sample</span></span>  
 <span data-ttu-id="43b78-116">Vea el [Entity Framework proveedor de ejemplo](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) para obtener un ejemplo de un proveedor de Entity Framework que admite un origen de datos distinto de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43b78-116">See the [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) for a sample of an Entity Framework provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43b78-117">En esta sección</span><span class="sxs-lookup"><span data-stu-id="43b78-117">In This Section</span></span>  
 [<span data-ttu-id="43b78-118">Generación de SQL</span><span class="sxs-lookup"><span data-stu-id="43b78-118">SQL Generation</span></span>](sql-generation.md)  
  
 [<span data-ttu-id="43b78-119">Generación de SQL de modificación</span><span class="sxs-lookup"><span data-stu-id="43b78-119">Modification SQL Generation</span></span>](modification-sql-generation.md)  
  
 [<span data-ttu-id="43b78-120">Especificación del manifiesto del proveedor</span><span class="sxs-lookup"><span data-stu-id="43b78-120">Provider Manifest Specification</span></span>](provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="43b78-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="43b78-121">See also</span></span>

- [<span data-ttu-id="43b78-122">Trabajo con proveedores de datos</span><span class="sxs-lookup"><span data-stu-id="43b78-122">Working with Data Providers</span></span>](working-with-data-providers.md)
