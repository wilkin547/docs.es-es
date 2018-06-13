---
title: Cuándo se debe implementar contenedores de Windows para instancias de contenedor de Azure (ACI)
description: Modernizar las aplicaciones .NET existentes con contenedores de Windows y de nube de Azure | Cuándo se debe implementar contenedores de Windows para instancias de contenedor de Azure (ACI)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/29/2018
ms.openlocfilehash: 3dc23c96543d9611763b571105f52b150dfec06f
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957955"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="a86e8-103">Cuándo se debe implementar contenedores de Windows para instancias de contenedor de Azure (ACI)</span><span class="sxs-lookup"><span data-stu-id="a86e8-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="a86e8-104">Instancias de contenedor propuesta de valor principal es que inmediatamente puede implementar contenedores en él y no es necesario mantener ese entorno de Azure, no necesita actualización/revisión en el sistema de operativo subyacentes o máquinas virtuales, todo lo que es transparente y acaba de implementar contenedores en un entorno de listos para usar.</span><span class="sxs-lookup"><span data-stu-id="a86e8-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlaying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="a86e8-105">Las razones y escenarios de cuándo es conveniente usar ACI son similares a los principales escenarios que, cuando se usa máquinas virtuales de Azure con los contenedores, por lo que básicamente, son los escenarios principales para usar instancias de contenedor de Azure:</span><span class="sxs-lookup"><span data-stu-id="a86e8-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

-   <span data-ttu-id="a86e8-106">**Escenarios de desarrollo/pruebas**</span><span class="sxs-lookup"><span data-stu-id="a86e8-106">**Dev/Test scenarios**</span></span>
-   <span data-ttu-id="a86e8-107">**Automatización de tareas**</span><span class="sxs-lookup"><span data-stu-id="a86e8-107">**Task automation**</span></span>
-   <span data-ttu-id="a86e8-108">**Agentes de CI/CD**</span><span class="sxs-lookup"><span data-stu-id="a86e8-108">**CI/CD agents**</span></span>
-   <span data-ttu-id="a86e8-109">**Procesamiento por lotes pequeños y la escala**</span><span class="sxs-lookup"><span data-stu-id="a86e8-109">**Small/scale batch processing**</span></span>
-   <span data-ttu-id="a86e8-110">**Aplicaciones web simples**</span><span class="sxs-lookup"><span data-stu-id="a86e8-110">**Simple web apps**</span></span>

<span data-ttu-id="a86e8-111">El escenario de aplicaciones web simple es un escenario razonable para ACI pero tenga en cuenta que, puesto que en ACI sólo puede tener una instancia del contenedor único por cada imagen de contenedor, no tiene una alta disponibilidad y solo se escalabilidad limitada.</span><span class="sxs-lookup"><span data-stu-id="a86e8-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="a86e8-112">Sin embargo, incluso cuando ACI se considera infraestructura porque solo proporciona instancias de contenedor único, hay una gran ventaja en comparación con regular máquinas virtuales de Azure con Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a86e8-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="a86e8-113">Con ACI, simplemente implementa los contenedores en un entorno mantiene automáticamente y solo paga por los contenedores.</span><span class="sxs-lookup"><span data-stu-id="a86e8-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="a86e8-114">No es necesario para mantener / / revisión de actualización de las máquinas virtuales, por lo que es una mejor plataforma para la mayoría de los escenarios donde puede que esté usando máquinas virtuales con contenedores.</span><span class="sxs-lookup"><span data-stu-id="a86e8-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="a86e8-115">Usar ACI es sencillo, simplemente implementar un contenedor, no es necesario para crear un entorno de máquinas virtuales solo implementar contenedores.</span><span class="sxs-lookup"><span data-stu-id="a86e8-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="a86e8-116">Las ventajas principales de instancias de contenedor de Azure (ACI) son:</span><span class="sxs-lookup"><span data-stu-id="a86e8-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

-   <span data-ttu-id="a86e8-117">Contenedores de ejecución sin tener que administrar servidores</span><span class="sxs-lookup"><span data-stu-id="a86e8-117">Run containers without managing servers</span></span>
-   <span data-ttu-id="a86e8-118">Aumentar la agilidad con contenedores a petición</span><span class="sxs-lookup"><span data-stu-id="a86e8-118">Increase agility with containers on demand</span></span>
-   <span data-ttu-id="a86e8-119">Implementar contenedores en la nube con sin precedentes simplicidad y velocidad, con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="a86e8-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span> 
-   <span data-ttu-id="a86e8-120">Proteger aplicaciones con aislamiento de hipervisor</span><span class="sxs-lookup"><span data-stu-id="a86e8-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="a86e8-121">En resumen, con ACI puede desarrollar aplicaciones rápidamente sin administrar máquinas virtuales ni tener que aprender nuevas herramientas.</span><span class="sxs-lookup"><span data-stu-id="a86e8-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="a86e8-122">Es simplemente la aplicación, en un contenedor, que se ejecuta en la nube.</span><span class="sxs-lookup"><span data-stu-id="a86e8-122">It's just your application, in a container, running in the cloud.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="a86e8-123">[Anterior](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Siguiente](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="a86e8-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
