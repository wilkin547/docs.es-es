---
title: "Cuándo se debe implementar contenedores de Windows en máquinas virtuales de Azure (IaaS nube)"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Cuándo se debe implementar contenedores de Windows en máquinas virtuales de Azure (IaaS nube)"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 832faed135d5b8ec9f8ad0a6ca82b5fac0273284
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a><span data-ttu-id="728a0-103">Cuándo se debe implementar contenedores de Windows en máquinas virtuales de Azure (IaaS nube)</span><span class="sxs-lookup"><span data-stu-id="728a0-103">When to deploy Windows Containers to Azure VMs (IaaS cloud)</span></span>

<span data-ttu-id="728a0-104">Si su organización está usando máquinas virtuales de Azure, incluso si también usa contenedores de Windows, siguen siendo ocuparse de IaaS.</span><span class="sxs-lookup"><span data-stu-id="728a0-104">If your organization is using Azure VMs, even if you are also using Windows Containers, you are still dealing with IaaS.</span></span> <span data-ttu-id="728a0-105">Esto significa que tratar con las operaciones de infraestructura, revisiones del sistema operativo de la máquina virtual y complejidad de la infraestructura para aplicaciones muy escalables cuando necesite implementar en varias máquinas virtuales en una infraestructura con equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="728a0-105">That means that dealing with infrastructure operations, VM OS patches, and infrastructure complexity for highly scalable applications when you need to deploy to multiple VMs in a load balanced infrastructure.</span></span> <span data-ttu-id="728a0-106">Los escenarios principales para usar los contenedores de Windows en una máquina virtual de Azure son:</span><span class="sxs-lookup"><span data-stu-id="728a0-106">The main scenarios for using Windows Containers in an Azure VM are:</span></span>

-   <span data-ttu-id="728a0-107">**Entorno de desarrollo/pruebas**: una VM en la nube es ideal para desarrollo y pruebas en la nube.</span><span class="sxs-lookup"><span data-stu-id="728a0-107">**Dev/test environment**: A VM in the cloud is perfect for development and testing in the cloud.</span></span> <span data-ttu-id="728a0-108">Puede crear rápidamente o detener el entorno según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="728a0-108">You can rapidly create or stop the environment depending on your needs.</span></span>

-   <span data-ttu-id="728a0-109">**Escalabilidad pequeña y mediana necesita**: en escenarios donde podría necesitar un par de máquinas virtuales para su entorno de producción, administra un pequeño número de máquinas virtuales podría estar asequible hasta que puede mover a los entornos de PaaS más avanzados, como orchestrators.</span><span class="sxs-lookup"><span data-stu-id="728a0-109">**Small and medium scalability needs**: In scenarios where you might need just a couple of VMs for your production environment, managing a small number of VMs might be affordable until you can move to more advanced PaaS environments, like orchestrators.</span></span>

-   <span data-ttu-id="728a0-110">**Entorno de producción con las herramientas de implementación existentes**: pueden mover desde un entorno local en el que se ha invertido en herramientas para realizar las implementaciones complejas en las máquinas virtuales o servidores de reconstrucción completa (por ejemplo, Puppet o herramientas similares).</span><span class="sxs-lookup"><span data-stu-id="728a0-110">**Production environment with existing deployment tools**: You might be moving from an on-premises environment in which you have invested in tools to make complex deployments to VMs or bare-metal servers (like Puppet or similar tools).</span></span> <span data-ttu-id="728a0-111">Para mover a la nube con unos cambios mínimos en los procedimientos de implementación del entorno de producción, puede continuar usar estas herramientas para implementar en máquinas virtuales de Azure.</span><span class="sxs-lookup"><span data-stu-id="728a0-111">To move to the cloud with minimal changes to production environment deployment procedures, you might continue to use those tools to deploy to Azure VMs.</span></span> <span data-ttu-id="728a0-112">Sin embargo, conviene utilizar contenedores de Windows como la unidad de implementación para mejorar la experiencia de implementación.</span><span class="sxs-lookup"><span data-stu-id="728a0-112">However, you'll want to use Windows Containers as the unit of deployment to improve the deployment experience.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="728a0-113">[Anterior](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Siguiente](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="728a0-113">[Previous](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
