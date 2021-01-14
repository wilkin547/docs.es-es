---
title: Migración a escenarios de nube híbrida
description: Modernización de las aplicaciones .NET existentes con Azure Clour y contenedores Windows | Migración a escenarios de nube híbrida
ms.date: 12/21/2020
ms.openlocfilehash: d5bf7f08381f3718061742b37c73604d8e57f1e2
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025230"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="a845b-103">Migración a escenarios de nube híbrida</span><span class="sxs-lookup"><span data-stu-id="a845b-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="a845b-104">Algunas organizaciones y empresas no pueden migrar algunas de sus aplicaciones a nubes públicas, como Microsoft Azure u otras nubes públicas, debido a las regulaciones o a sus propias directivas.</span><span class="sxs-lookup"><span data-stu-id="a845b-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="a845b-105">Sin embargo, es probable que cualquier organización pueda beneficiarse de tener algunas de sus aplicaciones en la nube pública y otras aplicaciones locales.</span><span class="sxs-lookup"><span data-stu-id="a845b-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="a845b-106">Pero un entorno mixto puede generar una complejidad excesiva en los entornos debido a las plataformas y tecnologías diferentes que se usan en las nubes públicas y los entornos locales.</span><span class="sxs-lookup"><span data-stu-id="a845b-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="a845b-107">Microsoft ofrece la mejor solución de nube híbrida, una en la que puede optimizar los recursos que tiene en el entorno local y en la nube pública y, al mismo tiempo, garantizar la coherencia en una nube híbrida de Azure.</span><span class="sxs-lookup"><span data-stu-id="a845b-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="a845b-108">Puede maximizar las aptitudes existentes y obtener un enfoque flexible y unificado para crear aplicaciones que se puedan ejecutar en la nube o en el entorno local, gracias a Azure Stack (local) y a Azure (nube pública).</span><span class="sxs-lookup"><span data-stu-id="a845b-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="a845b-109">En cuanto a la seguridad, puede centralizar la administración y la seguridad de toda la nube híbrida.</span><span class="sxs-lookup"><span data-stu-id="a845b-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="a845b-110">Puede tener el control de todos los recursos, desde su centro de datos a la nube, y proporcionar un inicio de sesión único a las aplicaciones locales y en la nube.</span><span class="sxs-lookup"><span data-stu-id="a845b-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="a845b-111">Para conseguir esta funcionalidad, puede extender Active Directory a una nube híbrida y usar la administración de identidades.</span><span class="sxs-lookup"><span data-stu-id="a845b-111">You accomplish this functionality by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="a845b-112">Por último, puede distribuir y analizar datos sin problemas, usar los mismos lenguajes de consulta para los recursos locales y en la nube, y aplicar análisis y aprendizaje profundo en Azure para enriquecer sus datos, independientemente de su origen.</span><span class="sxs-lookup"><span data-stu-id="a845b-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="a845b-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a845b-113">Azure Stack</span></span>

<span data-ttu-id="a845b-114">Azure Stack es una plataforma en la nube híbrida que permite proporcionar servicios de Azure desde el centro de datos de la organización.</span><span class="sxs-lookup"><span data-stu-id="a845b-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="a845b-115">Azure Stack está diseñado para posibilitar nuevas opciones para las aplicaciones modernas en escenarios clave, como los entornos perimetrales y los entornos desconectados, así como para resolver determinados requisitos de seguridad y de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a845b-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="a845b-116">En la figura 4-13 se muestra una visión general de la verdadera plataforma de nube híbrida que ofrece Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a845b-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Diagrama de la plataforma de nube híbrida de Microsoft con Azure Stack y Azure.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="a845b-118">**Figura 4-13.**</span><span class="sxs-lookup"><span data-stu-id="a845b-118">**Figure 4-13.**</span></span> <span data-ttu-id="a845b-119">Plataforma de nube híbrida de Microsoft con Azure Stack y Azure</span><span class="sxs-lookup"><span data-stu-id="a845b-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="a845b-120">Azure Stack se ofrece en dos opciones de implementación para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="a845b-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="a845b-121">Sistemas integrados de Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a845b-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="a845b-122">Kit de desarrollo de Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a845b-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="a845b-123">Sistemas integrados de Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a845b-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="a845b-124">Los sistemas integrados de Azure Stack los ofrecen conjuntamente Microsoft y sus asociados de hardware.</span><span class="sxs-lookup"><span data-stu-id="a845b-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="a845b-125">Esta asociación crea una solución que ofrece innovación al ritmo de la nube, equilibrada con la simplicidad de la administración.</span><span class="sxs-lookup"><span data-stu-id="a845b-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="a845b-126">Dado que Azure Stack se ofrece como un sistema integrado de hardware y software, obtiene la cantidad adecuada de flexibilidad y control, a la vez que sigue adoptando la innovación de la nube.</span><span class="sxs-lookup"><span data-stu-id="a845b-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="a845b-127">El tamaño de los sistemas integrados de Azure Stack va de los 4 a los 12 nodos y tiene un soporte técnico conjunto que ofrecen un asociado de hardware y Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a845b-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="a845b-128">Use los sistemas integrados de Azure Stack para implementar nuevos escenarios para las cargas de trabajo de producción.</span><span class="sxs-lookup"><span data-stu-id="a845b-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="a845b-129">Kit de desarrollo de Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a845b-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="a845b-130">El Kit de desarrollo de Microsoft Azure Stack es una implementación de un solo nodo de Azure Stack, que puede usar para evaluar y obtener información sobre Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="a845b-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="a845b-131">También puede usar el Kit de desarrollo de Azure Stack como entorno de desarrollo, donde puede desarrollar con API y herramientas coherentes con Azure.</span><span class="sxs-lookup"><span data-stu-id="a845b-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="a845b-132">El Kit de desarrollo de Azure Stack no está diseñado para usarse como un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="a845b-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a845b-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a845b-133">Additional resources</span></span>

- <span data-ttu-id="a845b-134">**Nube híbrida de Azure**</span><span class="sxs-lookup"><span data-stu-id="a845b-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="a845b-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="a845b-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="a845b-136">**Cuentas de servicio de Active Directory para contenedores Windows**</span><span class="sxs-lookup"><span data-stu-id="a845b-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="a845b-137">**Creación de un contenedor con compatibilidad con Active Directory**</span><span class="sxs-lookup"><span data-stu-id="a845b-137">**Create a container with Active Directory support**</span></span>

    <https://docs.microsoft.com/archive/blogs/containerstuff/create-a-container-with-active-directory-support>

- <span data-ttu-id="a845b-138">**Licencias para la Ventaja híbrida de Azure**</span><span class="sxs-lookup"><span data-stu-id="a845b-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="a845b-139">[Anterior](life-cycle-ci-cd-pipelines-devops-tools.md)
>[Siguiente](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a845b-139">[Previous](life-cycle-ci-cd-pipelines-devops-tools.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
