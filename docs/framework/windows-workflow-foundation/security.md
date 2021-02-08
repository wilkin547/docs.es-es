---
description: 'Más información sobre: seguridad'
title: Seguridad
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: 8f095292deac77c1c72cf87a93064569f7dab982
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798100"
---
# <a name="security"></a><span data-ttu-id="fdedd-103">Seguridad</span><span class="sxs-lookup"><span data-stu-id="fdedd-103">Security</span></span>

<span data-ttu-id="fdedd-104">El almacén de instancias de flujo de trabajo de SQL usa los siguientes roles de seguridad de base de datos para garantizar el acceso a la información de estado de las instancias en la base de datos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="fdedd-104">The SQL Workflow Instance Store uses the following database security roles to secure access to instance state information in the persistence database.</span></span>  
  
- <span data-ttu-id="fdedd-105">**System. Activities. DurableInstancing. InstanceStoreUsers**.</span><span class="sxs-lookup"><span data-stu-id="fdedd-105">**System.Activities.DurableInstancing.InstanceStoreUsers**.</span></span> <span data-ttu-id="fdedd-106">Este rol dispone de acceso de lectura y escritura a las vistas públicas y de derechos de ejecución en procedimientos almacenados relacionados con la creación, la carga y el almacenamiento de instancias.</span><span class="sxs-lookup"><span data-stu-id="fdedd-106">This role has read and write access to public views and execution rights to stored procedures that are involved in creating, loading and saving instances.</span></span>  
  
- <span data-ttu-id="fdedd-107">**System. Activities. DurableInstancing. InstanceStoreObservers**.</span><span class="sxs-lookup"><span data-stu-id="fdedd-107">**System.Activities.DurableInstancing.InstanceStoreObservers**.</span></span> <span data-ttu-id="fdedd-108">Este rol tiene acceso de solo lectura a las vistas públicas.</span><span class="sxs-lookup"><span data-stu-id="fdedd-108">This role has read-only access to public views.</span></span>  
  
- <span data-ttu-id="fdedd-109">**System. Activities. DurableInstancing. WorkflowActivationUsers**.</span><span class="sxs-lookup"><span data-stu-id="fdedd-109">**System.Activities.DurableInstancing.WorkflowActivationUsers**.</span></span> <span data-ttu-id="fdedd-110">Este rol posee derechos de ejecución a procedimientos almacenados que están involucrados en el proceso de activación de instancias.</span><span class="sxs-lookup"><span data-stu-id="fdedd-110">This role has execution rights to stored procedures that are involved in the instance activation process.</span></span> <span data-ttu-id="fdedd-111">Para obtener más información sobre la activación de instancias, vea [activación de instancias](instance-activation.md).</span><span class="sxs-lookup"><span data-stu-id="fdedd-111">For more information about instance activation, see [Instance Activation](instance-activation.md).</span></span> <span data-ttu-id="fdedd-112">La cuenta de usuario con la que se ejecuta un host genérico (como el servicio de administración de flujos de trabajo de las características de hospedaje de Windows Server AppFabric) debe agregarse a este rol de base de datos.</span><span class="sxs-lookup"><span data-stu-id="fdedd-112">The user account under which a generic host (such as the Workflow Management Service of the hosting features of Windows Server AppFabric) runs should be added to this database role.</span></span>  
  
 <span data-ttu-id="fdedd-113">Para más información sobre la seguridad de los almacenes de persistencia con Windows Server App fabric, consulte [configuración de seguridad para almacenes de persistencia en App fabric](/previous-versions/appfabric/ff431727(v=azure.10)) .</span><span class="sxs-lookup"><span data-stu-id="fdedd-113">For more information about security for persistence stores with Windows Server App Fabric, see [Security Configuration for Persistence Stores in App Fabric](/previous-versions/appfabric/ff431727(v=azure.10))</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="fdedd-114">Un cliente que tiene acceso a sus propios datos de instancia en el almacén de instancias tendrá acceso al resto de instancias en el mismo almacén de instancias.</span><span class="sxs-lookup"><span data-stu-id="fdedd-114">A client that has access to its own instance data in the instance store has access to all other instances in the same instance store.</span></span> <span data-ttu-id="fdedd-115">El almacén de instancias no permite especificar permisos de seguridad en el nivel de instancias.</span><span class="sxs-lookup"><span data-stu-id="fdedd-115">The instance store does not support specifying security permissions at the instance level.</span></span> <span data-ttu-id="fdedd-116">Debería crear almacenes de instancias independientes y asignar distintos grupos/usuarios para que tengan acceso a almacenes diferentes.</span><span class="sxs-lookup"><span data-stu-id="fdedd-116">You should create separate instance stores and map different groups/users to have access to different stores.</span></span>
