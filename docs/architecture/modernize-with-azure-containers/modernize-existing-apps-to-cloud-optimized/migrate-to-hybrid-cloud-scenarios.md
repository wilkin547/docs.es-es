---
title: Migración a escenarios de nube híbrida
description: Modernización de las aplicaciones .NET existentes con la nube de Azure y los contenedores de Windows | Migración a escenarios de nube híbrida
ms.date: 04/30/2018
ms.openlocfilehash: 5f0819495080bc29ed1239b4a7ab8af31141881b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318466"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="8ae91-103">Migración a escenarios de nube híbrida</span><span class="sxs-lookup"><span data-stu-id="8ae91-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="8ae91-104">Algunas organizaciones y empresas no pueden migrar algunas de sus aplicaciones a nubes públicas como Microsoft Azure o cualquier otra nube pública debido a las regulaciones o a sus propias directivas.</span><span class="sxs-lookup"><span data-stu-id="8ae91-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="8ae91-105">Sin embargo, es probable que cualquier organización pueda beneficiarse de tener algunas de sus aplicaciones en la nube pública y en otras aplicaciones locales.</span><span class="sxs-lookup"><span data-stu-id="8ae91-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="8ae91-106">Pero un entorno mixto puede conducir a una complejidad excesiva en entornos debido a diferentes plataformas y tecnologías que se usan en nubes públicas frente a entornos locales.</span><span class="sxs-lookup"><span data-stu-id="8ae91-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="8ae91-107">Microsoft ofrece la mejor solución de nube híbrida, una en la que puede optimizar sus recursos locales y en la nube pública, al tiempo que garantiza la coherencia en una nube híbrida de Azure.</span><span class="sxs-lookup"><span data-stu-id="8ae91-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="8ae91-108">Puede maximizar los conocimientos existentes y obtener un enfoque flexible y unificado para crear aplicaciones que se puedan ejecutar en la nube o de forma local, gracias a Azure Stack (local) y a Azure (nube pública).</span><span class="sxs-lookup"><span data-stu-id="8ae91-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="8ae91-109">En cuanto a la seguridad, puede centralizar la administración y la seguridad en toda la nube híbrida.</span><span class="sxs-lookup"><span data-stu-id="8ae91-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="8ae91-110">Puede obtener el control sobre todos los recursos, desde su centro de recursos a la nube, proporcionando inicio de sesión único a aplicaciones locales y en la nube.</span><span class="sxs-lookup"><span data-stu-id="8ae91-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="8ae91-111">Para ello, puede extender Active Directory a una nube híbrida y mediante el uso de la administración de identidades.</span><span class="sxs-lookup"><span data-stu-id="8ae91-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="8ae91-112">Por último, puede distribuir y analizar datos sin problemas, usar los mismos lenguajes de consulta para los recursos locales y en la nube, y aplicar análisis y aprendizaje profundo en Azure para enriquecer sus datos, independientemente de su origen.</span><span class="sxs-lookup"><span data-stu-id="8ae91-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="8ae91-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="8ae91-113">Azure Stack</span></span>

<span data-ttu-id="8ae91-114">Azure Stack es una plataforma en la nube híbrida que le permite ofrecer servicios de Azure desde el centro de recursos de su organización.</span><span class="sxs-lookup"><span data-stu-id="8ae91-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="8ae91-115">Azure Stack está diseñado para admitir nuevas opciones para las aplicaciones modernas en escenarios clave, como entornos perimetrales y no conectados, o para cumplir los requisitos específicos de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="8ae91-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="8ae91-116">En la figura 4-13 se muestra una visión general de la verdadera plataforma en la nube híbrida que ofrece Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ae91-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Diagrama de la plataforma de nube híbrida de Microsoft con Azure Stack y Azure.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="8ae91-118">**Figura 4-13.**</span><span class="sxs-lookup"><span data-stu-id="8ae91-118">**Figure 4-13.**</span></span> <span data-ttu-id="8ae91-119">Plataforma de nube híbrida de Microsoft con Azure Stack y Azure</span><span class="sxs-lookup"><span data-stu-id="8ae91-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="8ae91-120">Azure Stack se ofrece en dos opciones de implementación, para satisfacer sus necesidades:</span><span class="sxs-lookup"><span data-stu-id="8ae91-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="8ae91-121">Sistemas integrados Azure Stack</span><span class="sxs-lookup"><span data-stu-id="8ae91-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="8ae91-122">Kit de desarrollo de Azure Stack</span><span class="sxs-lookup"><span data-stu-id="8ae91-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="8ae91-123">Sistemas integrados Azure Stack</span><span class="sxs-lookup"><span data-stu-id="8ae91-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="8ae91-124">Azure Stack sistemas integrados se ofrecen a través de una asociación de Microsoft y de asociados de hardware.</span><span class="sxs-lookup"><span data-stu-id="8ae91-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="8ae91-125">La Asociación crea una solución que ofrece innovación en el ritmo de la nube que se equilibra con simplicidad en la administración.</span><span class="sxs-lookup"><span data-stu-id="8ae91-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="8ae91-126">Dado que Azure Stack se ofrece como un sistema integrado de hardware y software, obtiene la cantidad adecuada de flexibilidad y control, a la vez que sigue adoptando la innovación de la nube.</span><span class="sxs-lookup"><span data-stu-id="8ae91-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="8ae91-127">Azure Stack sistemas integrados tienen un tamaño de entre 4 y 12 nodos y se admiten conjuntamente por el asociado de hardware y Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8ae91-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="8ae91-128">Use Azure Stack sistemas integrados para implementar nuevos escenarios para las cargas de trabajo de producción.</span><span class="sxs-lookup"><span data-stu-id="8ae91-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="8ae91-129">Kit de desarrollo de Azure Stack</span><span class="sxs-lookup"><span data-stu-id="8ae91-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="8ae91-130">Microsoft Azure Stack kit de desarrollo es una implementación de un solo nodo de Azure Stack, que puede usar para evaluar y obtener información sobre Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="8ae91-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="8ae91-131">También puede usar Kit de desarrollo de Azure Stack como entorno de desarrollo, donde puede desarrollar con las API y las herramientas que son coherentes con Azure.</span><span class="sxs-lookup"><span data-stu-id="8ae91-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="8ae91-132">Kit de desarrollo de Azure Stack no está diseñado para usarse como un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="8ae91-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="8ae91-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8ae91-133">Additional resources</span></span>

- <span data-ttu-id="8ae91-134">**Nube híbrida de Azure**</span><span class="sxs-lookup"><span data-stu-id="8ae91-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="8ae91-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="8ae91-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="8ae91-136">**Active Directory cuentas de servicio para contenedores de Windows**</span><span class="sxs-lookup"><span data-stu-id="8ae91-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="8ae91-137">**Creación de un contenedor con compatibilidad con Active Directory**</span><span class="sxs-lookup"><span data-stu-id="8ae91-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="8ae91-138">**Licencias de Ventaja híbrida de Azure**</span><span class="sxs-lookup"><span data-stu-id="8ae91-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="8ae91-139">[Anterior](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Siguiente](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8ae91-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
