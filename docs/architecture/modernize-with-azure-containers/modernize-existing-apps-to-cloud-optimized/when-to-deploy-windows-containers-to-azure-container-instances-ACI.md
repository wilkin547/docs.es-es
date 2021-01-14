---
title: Cuándo se deben implementar contenedores Windows en Azure Container Instances (ACI)
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Cuándo se deben implementar contenedores Windows en Azure Container Instances (ACI)
ms.date: 12/21/2020
ms.openlocfilehash: 556fe7cbec7d259db9ec886b777feda9eed09116
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025138"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="4492c-103">Cuándo se deben implementar contenedores Windows en Azure Container Instances (ACI)</span><span class="sxs-lookup"><span data-stu-id="4492c-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="4492c-104">La propuesta de valor principal de Azure Container Instances es que puede implementar contenedores en él y no es necesario mantener ese entorno ni actualizar o aplicar revisiones al sistema operativo o las máquinas virtuales subyacentes; todo eso es transparente y solo se implementan contenedores en un entorno listo para usar.</span><span class="sxs-lookup"><span data-stu-id="4492c-104">The main value proposition of Azure Container Instances is that you can right away deploy containers to it and you don't need to maintain that environment, you don't need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="4492c-105">Los motivos y los escenarios en los que sería conveniente usar ACI son similares a los principales escenarios en los que se usan máquinas virtuales de Azure con contenedores, por lo que, básicamente, los principales escenarios donde se usa Azure Container Instances son:</span><span class="sxs-lookup"><span data-stu-id="4492c-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="4492c-106">**Escenarios de desarrollo y pruebas**</span><span class="sxs-lookup"><span data-stu-id="4492c-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="4492c-107">**Automatización de tareas**</span><span class="sxs-lookup"><span data-stu-id="4492c-107">**Task automation**</span></span>
- <span data-ttu-id="4492c-108">**Agentes de CI/CD**</span><span class="sxs-lookup"><span data-stu-id="4492c-108">**CI/CD agents**</span></span>
- <span data-ttu-id="4492c-109">**Procesamiento por lotes a pequeña o gran escala**</span><span class="sxs-lookup"><span data-stu-id="4492c-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="4492c-110">**Aplicaciones web sencillas**</span><span class="sxs-lookup"><span data-stu-id="4492c-110">**Simple web apps**</span></span>

<span data-ttu-id="4492c-111">El escenario de aplicaciones web sencillo es apto para ACI, pero tenga en cuenta que, como en ACI solo puede haber una instancia de contenedor única por cada imagen de contenedor, no tendrá alta disponibilidad y tendrá una escalabilidad limitada.</span><span class="sxs-lookup"><span data-stu-id="4492c-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won't have high availability and only have limited scalability.</span></span>

<span data-ttu-id="4492c-112">Sin embargo, aunque ACI se considera infraestructura porque solo proporciona instancias de contenedor únicas, existe una gran ventaja en comparación con las máquinas virtuales de Azure normales con Windows Server.</span><span class="sxs-lookup"><span data-stu-id="4492c-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="4492c-113">Con ACI, solo tiene que implementar los contenedores en un entorno autohospedado y solo paga por esos contenedores.</span><span class="sxs-lookup"><span data-stu-id="4492c-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="4492c-114">No es necesario mantener, actualizar ni aplicar revisiones a las máquinas virtuales, por lo que es una plataforma mucho mejor para la mayoría de los escenarios en los que podría estar usando máquinas virtuales con contenedores.</span><span class="sxs-lookup"><span data-stu-id="4492c-114">You don't need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="4492c-115">El uso de ACI es sencillo, solo tiene que implementar un contenedor; no es necesario crear un entorno de máquina virtual que solo implemente contenedores.</span><span class="sxs-lookup"><span data-stu-id="4492c-115">Using ACI is straight forward, you just deploy a container, there's no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="4492c-116">Las principales ventajas de Azure Container Instances (ACI) son:</span><span class="sxs-lookup"><span data-stu-id="4492c-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="4492c-117">Ejecución de contenedores sin administrar servidores</span><span class="sxs-lookup"><span data-stu-id="4492c-117">Run containers without managing servers</span></span>
- <span data-ttu-id="4492c-118">Aumento de la agilidad con contenedores a petición</span><span class="sxs-lookup"><span data-stu-id="4492c-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="4492c-119">Implementación de contenedores en la nube con una simplicidad y una velocidad sin precedentes, con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="4492c-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="4492c-120">Protección de aplicaciones con aislamiento de hipervisor</span><span class="sxs-lookup"><span data-stu-id="4492c-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="4492c-121">En resumen, con ACI puede desarrollar aplicaciones rápidamente sin tener que administrar máquinas virtuales ni aprender nuevas herramientas.</span><span class="sxs-lookup"><span data-stu-id="4492c-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="4492c-122">Solo necesita su aplicación, en un contenedor, ejecutándose en la nube.</span><span class="sxs-lookup"><span data-stu-id="4492c-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="4492c-123">[Anterior](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Siguiente](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="4492c-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)</span></span>
