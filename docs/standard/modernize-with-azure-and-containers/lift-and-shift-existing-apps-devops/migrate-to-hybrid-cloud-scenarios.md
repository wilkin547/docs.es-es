---
title: "Migrar a escenarios de nube híbrida"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Migrar a escenarios de nube híbrida"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/2/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6216068786745ac4ebc00263a14b4afe247193f5
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2018
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="3ab92-103">Migrar a escenarios de nube híbrida</span><span class="sxs-lookup"><span data-stu-id="3ab92-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="3ab92-104">Algunas organizaciones y empresas no pueden migrar algunos de sus aplicaciones a nubes públicas como Microsoft Azure o cualquier otra nube pública debido a la normativa o sus propias directivas.</span><span class="sxs-lookup"><span data-stu-id="3ab92-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="3ab92-105">Sin embargo, es probable que cualquier organización puede beneficiarse de tener algunos de sus aplicaciones en la nube pública y otras aplicaciones locales.</span><span class="sxs-lookup"><span data-stu-id="3ab92-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="3ab92-106">Pero puede provocar un entorno mixto excesiva complejidad en los entornos debido a distintas plataformas y tecnologías que se usan en nubes públicas frente a entornos locales.</span><span class="sxs-lookup"><span data-stu-id="3ab92-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="3ab92-107">Microsoft proporciona la mejor solución de nube híbrida, uno en el que se pueden optimizar sus activos existentes en local y en la nube pública, mientras se asegura la coherencia en una nube híbrida de Azure.</span><span class="sxs-lookup"><span data-stu-id="3ab92-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="3ab92-108">Puede maximizar los conocimientos y obtener un enfoque flexible y unificado para la generación de aplicaciones que se ejecutan en la nube o local, gracias a la pila de Azure (local) y Azure (nube pública).</span><span class="sxs-lookup"><span data-stu-id="3ab92-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="3ab92-109">En cuanto a seguridad, puede centralizar la administración y la seguridad a través de la nube híbrida.</span><span class="sxs-lookup"><span data-stu-id="3ab92-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="3ab92-110">Puede obtener un control sobre todos los recursos, desde el centro de datos en la nube, proporcionando un inicio de sesión único a local y las aplicaciones de nube.</span><span class="sxs-lookup"><span data-stu-id="3ab92-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="3ab92-111">Esto se consigue mediante la extensión de Active Directory a una nube híbrida y mediante el uso de administración de identidades.</span><span class="sxs-lookup"><span data-stu-id="3ab92-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="3ab92-112">Por último, puede distribuir y analizar los datos sin problemas, use los mismos lenguajes de consulta para los activos en la nube y locales y aplicar profunda de aprendizaje de Azure para enriquecer los datos, independientemente de su origen y análisis.</span><span class="sxs-lookup"><span data-stu-id="3ab92-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="3ab92-113">Pila de Azure</span><span class="sxs-lookup"><span data-stu-id="3ab92-113">Azure Stack</span></span>

<span data-ttu-id="3ab92-114">Pila de Azure es una plataforma de nube híbrida que le permite ofrecer servicios de Azure desde el centro de datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="3ab92-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="3ab92-115">Pila de Azure está diseñado para admitir nuevas opciones para las aplicaciones modernas en escenarios claves, como el borde y entornos no conectados o resolver determinados requisitos de seguridad y cumplimiento de normas.</span><span class="sxs-lookup"><span data-stu-id="3ab92-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="3ab92-116">Figura 4-13 muestra una visión general de la plataforma de nube híbrida true que ofrece Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ab92-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Plataforma de nube híbrida de Microsoft con la pila de Azure y Azure](./media/image13.jpg)

> <span data-ttu-id="3ab92-118">**Figura 4-13.**</span><span class="sxs-lookup"><span data-stu-id="3ab92-118">**Figure 4-13.**</span></span> <span data-ttu-id="3ab92-119">Plataforma de nube híbrida de Microsoft con la pila de Azure y Azure</span><span class="sxs-lookup"><span data-stu-id="3ab92-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="3ab92-120">Pila de Azure se ofrece en dos opciones de implementación, para satisfacer sus necesidades:</span><span class="sxs-lookup"><span data-stu-id="3ab92-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

-   <span data-ttu-id="3ab92-121">Sistemas integrados de pila de Azure</span><span class="sxs-lookup"><span data-stu-id="3ab92-121">Azure Stack integrated systems</span></span>

-   <span data-ttu-id="3ab92-122">Kit de desarrollo de la pila de Azure</span><span class="sxs-lookup"><span data-stu-id="3ab92-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="3ab92-123">Sistemas integrados de pila de Azure</span><span class="sxs-lookup"><span data-stu-id="3ab92-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="3ab92-124">Sistemas de pila integrada Azure se ofrecen a través de una asociación de asociados de Microsoft y hardware.</span><span class="sxs-lookup"><span data-stu-id="3ab92-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="3ab92-125">El perfil crea una solución que ofrece innovación paced en la nube que se equilibra con simplicidad de administración.</span><span class="sxs-lookup"><span data-stu-id="3ab92-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="3ab92-126">Ya que Azure pila se ofrece como un sistema integrado de hardware y software, obtendrá la cantidad correcta de flexibilidad y control, mientras todavía adopta innovación de la nube.</span><span class="sxs-lookup"><span data-stu-id="3ab92-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="3ab92-127">Sistemas de pila integrada Azure varían en tamaño de 4 a 12 nodos y conjuntamente son compatibles con los socios de hardware y Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ab92-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="3ab92-128">Usar sistemas de pila de Azure integrado para implementar nuevos escenarios para las cargas de trabajo de producción.</span><span class="sxs-lookup"><span data-stu-id="3ab92-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="3ab92-129">Kit de desarrollo de la pila de Azure</span><span class="sxs-lookup"><span data-stu-id="3ab92-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="3ab92-130">Kit de desarrollo de pila de Microsoft Azure es una implementación de un único nodo de pila de Azure, lo que puede usar para evaluar y obtener información sobre la pila de Azure.</span><span class="sxs-lookup"><span data-stu-id="3ab92-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="3ab92-131">También puede usar el Kit de desarrollo de pila de Azure como un entorno de desarrollador, donde puede desarrollar con las API y herramientas que son coherentes con Azure.</span><span class="sxs-lookup"><span data-stu-id="3ab92-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="3ab92-132">Kit de desarrollo de pila de Azure no está pensado para usarse como un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="3ab92-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="3ab92-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3ab92-133">Additional resources</span></span>

-   <span data-ttu-id="3ab92-134">**Nube híbrida de Azure**</span><span class="sxs-lookup"><span data-stu-id="3ab92-134">**Azure hybrid cloud**</span></span>

    [<span data-ttu-id="3ab92-135">https://www.microsoft.com/cloud-platform/hybrid-cloud</span><span class="sxs-lookup"><span data-stu-id="3ab92-135">https://www.microsoft.com/cloud-platform/hybrid-cloud</span></span>](https://www.microsoft.com/cloud-platform/hybrid-cloud)

-   <span data-ttu-id="3ab92-136">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="3ab92-136">**Azure Stack**</span></span>

    [<span data-ttu-id="3ab92-137">https://azure.microsoft.com/overview/azure-stack/</span><span class="sxs-lookup"><span data-stu-id="3ab92-137">https://azure.microsoft.com/overview/azure-stack/</span></span>](https://azure.microsoft.com/overview/azure-stack/)

-   <span data-ttu-id="3ab92-138">**Cuentas de servicio de Active Directory para los contenedores de Windows**</span><span class="sxs-lookup"><span data-stu-id="3ab92-138">**Active Directory Service Accounts for Windows Containers**</span></span>

    [<span data-ttu-id="3ab92-139">https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts</span><span class="sxs-lookup"><span data-stu-id="3ab92-139">https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts)

-   <span data-ttu-id="3ab92-140">**Crear un contenedor con compatibilidad con Active Directory**</span><span class="sxs-lookup"><span data-stu-id="3ab92-140">**Create a container with Active Directory support**</span></span>

    [<span data-ttu-id="3ab92-141">https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/</span><span class="sxs-lookup"><span data-stu-id="3ab92-141">https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/</span></span>](https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/)

-   <span data-ttu-id="3ab92-142">**Licencias de beneficio híbrida de Azure**</span><span class="sxs-lookup"><span data-stu-id="3ab92-142">**Azure Hybrid Benefit licensing**</span></span>

    [<span data-ttu-id="3ab92-143">https://azure.microsoft.com/pricing/hybrid-use-benefit/</span><span class="sxs-lookup"><span data-stu-id="3ab92-143">https://azure.microsoft.com/pricing/hybrid-use-benefit/</span></span>](https://azure.microsoft.com/pricing/hybrid-use-benefit/)

>[!div class="step-by-step"]
<span data-ttu-id="3ab92-144">[Anterior](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Siguiente](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3ab92-144">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
