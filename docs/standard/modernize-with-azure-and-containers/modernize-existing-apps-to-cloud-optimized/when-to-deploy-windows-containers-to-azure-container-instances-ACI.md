---
title: Cuándo se deben implementar contenedores de Windows Azure Container Instances (ACI)
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Cuándo se deben implementar contenedores de Windows Azure Container Instances (ACI)
ms.date: 04/29/2018
ms.openlocfilehash: 9bfa0688d07bd04964a1b28f688f125b5bcd2299
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638923"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-instances-aci"></a><span data-ttu-id="94eed-103">Cuándo se deben implementar contenedores de Windows Azure Container Instances (ACI)</span><span class="sxs-lookup"><span data-stu-id="94eed-103">When to deploy Windows Containers to Azure Container Instances (ACI)</span></span>

<span data-ttu-id="94eed-104">Azure Container Instances propuesta de valor principal es que inmediatamente puede implementar contenedores en él y no es necesario mantener ese entorno, no es necesario actualizar/aplicar revisiones del sistema operativo o las máquinas virtuales, todo lo que es transparente subyacente y acaba de implementar contenedores en un entorno listos para usar.</span><span class="sxs-lookup"><span data-stu-id="94eed-104">Azure Container Instances main value proposition is that you can right away deploy containers to it and you don’t need to maintain that environment, you don’t need to upgrade/patch the underlying operating system or VMs, all that is transparent and you just deploy containers into a ready-to-use environment.</span></span>

<span data-ttu-id="94eed-105">Los escenarios cuando desee utilizar ACI y motivos son similares a los escenarios principales al usar máquinas virtuales de Azure con contenedores, básicamente, los escenarios principales para usar Azure Container Instances son:</span><span class="sxs-lookup"><span data-stu-id="94eed-105">The reasons and scenarios when you would want to use ACI are similar to the main scenarios when you use Azure VMs with containers, so basically, the main scenarios for using Azure Container Instances are:</span></span>

- <span data-ttu-id="94eed-106">**Escenarios de desarrollo/pruebas**</span><span class="sxs-lookup"><span data-stu-id="94eed-106">**Dev/Test scenarios**</span></span>
- <span data-ttu-id="94eed-107">**Automatización de tareas**</span><span class="sxs-lookup"><span data-stu-id="94eed-107">**Task automation**</span></span>
- <span data-ttu-id="94eed-108">**Agentes de CI/CD**</span><span class="sxs-lookup"><span data-stu-id="94eed-108">**CI/CD agents**</span></span>
- <span data-ttu-id="94eed-109">**Procesamiento por lotes de pequeño o escala**</span><span class="sxs-lookup"><span data-stu-id="94eed-109">**Small/scale batch processing**</span></span>
- <span data-ttu-id="94eed-110">**Aplicaciones web sencillas**</span><span class="sxs-lookup"><span data-stu-id="94eed-110">**Simple web apps**</span></span>

<span data-ttu-id="94eed-111">Las aplicaciones web simple es un escenario razonable para ACI, pero tenga en cuenta que dado que en Azure Container Instances solo puede tener una instancia de contenedor único por cada imagen de contenedor, no tendrá alta disponibilidad y solo tienen una limitada escalabilidad.</span><span class="sxs-lookup"><span data-stu-id="94eed-111">The simple web apps scenario is a fair scenario for ACI but take into account that since in ACI you can only have a single container instance per container image, you won’t have high availability and only have limited scalability.</span></span>

<span data-ttu-id="94eed-112">Sin embargo, incluso cuando ACI se considere como infraestructura porque simplemente proporciona instancias de contenedor único, hay una enorme ventaja en comparación con las máquinas virtuales de Azure normales con Windows Server.</span><span class="sxs-lookup"><span data-stu-id="94eed-112">However, even when ACI is considered infrastructure because it just provides single container instances, there is a huge benefit compared to regular Azure VMs with Windows Server.</span></span> <span data-ttu-id="94eed-113">Con ACI, solo implementa los contenedores en un entorno de mantenimiento automático y solo paga por los contenedores.</span><span class="sxs-lookup"><span data-stu-id="94eed-113">With ACI, you just deploy the containers into a self-maintained environment and you just pay for those containers.</span></span> <span data-ttu-id="94eed-114">No es necesario para mantener, actualizaciones o revisiones de máquinas virtuales, por lo que es una mejor plataforma para la mayoría de los escenarios donde puede que esté usando máquinas virtuales con contenedores.</span><span class="sxs-lookup"><span data-stu-id="94eed-114">You don’t need to maintain/update/patch VMs, so it is a much better platform for most scenarios where you might be using VMs with containers.</span></span> <span data-ttu-id="94eed-115">Utilizando ACI es sencilla, simplemente implementar un contenedor, no hay ninguna necesidad de crear un entorno de máquinas virtuales basta con implementar contenedores.</span><span class="sxs-lookup"><span data-stu-id="94eed-115">Using ACI is straight forward, you just deploy a container, there’s no need to create a VM environment you just deploy containers.</span></span>

<span data-ttu-id="94eed-116">Las principales ventajas de Azure Container Instances (ACI) son:</span><span class="sxs-lookup"><span data-stu-id="94eed-116">The main benefits of Azure Container Instances (ACI) are:</span></span>

- <span data-ttu-id="94eed-117">Ejecute contenedores sin administrar servidores</span><span class="sxs-lookup"><span data-stu-id="94eed-117">Run containers without managing servers</span></span>
- <span data-ttu-id="94eed-118">Aumentar la agilidad con contenedores a petición</span><span class="sxs-lookup"><span data-stu-id="94eed-118">Increase agility with containers on demand</span></span>
- <span data-ttu-id="94eed-119">Implementar contenedores en la nube con una velocidad y una simplicidad sin precedentes, con un solo comando.</span><span class="sxs-lookup"><span data-stu-id="94eed-119">Deploy containers to the cloud with unprecedented simplicity and speed—with a single command.</span></span>
- <span data-ttu-id="94eed-120">Aplicaciones seguras con aislamiento de hipervisor</span><span class="sxs-lookup"><span data-stu-id="94eed-120">Secure applications with hypervisor isolation</span></span>

<span data-ttu-id="94eed-121">En resumen, con ACI puede desarrollar aplicaciones rápidamente sin administrar máquinas virtuales ni tener que aprender nuevas herramientas.</span><span class="sxs-lookup"><span data-stu-id="94eed-121">In short, with ACI you can develop apps fast without managing virtual machines or having to learn new tools.</span></span> <span data-ttu-id="94eed-122">Es simplemente la aplicación en un contenedor, que se ejecutan en la nube.</span><span class="sxs-lookup"><span data-stu-id="94eed-122">It's just your application, in a container, running in the cloud.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="94eed-123">[Anterior](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
> [Siguiente](when-to-deploy-windows-containers-to-service-fabric.md)</span><span class="sxs-lookup"><span data-stu-id="94eed-123">[Previous](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[Next](when-to-deploy-windows-containers-to-service-fabric.md)</span></span>
