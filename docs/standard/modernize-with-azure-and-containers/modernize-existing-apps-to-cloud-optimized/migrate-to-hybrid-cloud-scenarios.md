---
title: Migración a escenarios de nube híbrida
description: Modernizar aplicaciones .NET existentes con contenedores de Windows y la nube de Azure | Migrar a escenarios de nube híbrida
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 6cba29ad654b09b01f9b6969fa6688dd5f165fbb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64636590"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="a88d8-103">Migración a escenarios de nube híbrida</span><span class="sxs-lookup"><span data-stu-id="a88d8-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="a88d8-104">Algunas organizaciones y empresas no pueden migrar algunos de sus aplicaciones a nubes públicas, como Microsoft Azure o cualquier otra nube pública debido a las regulaciones o sus propias directivas.</span><span class="sxs-lookup"><span data-stu-id="a88d8-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="a88d8-105">Sin embargo, es probable que cualquier organización puede beneficiarse de tener algunas de sus aplicaciones en la nube pública y otras aplicaciones locales.</span><span class="sxs-lookup"><span data-stu-id="a88d8-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="a88d8-106">Pero un entorno mixto puede dar lugar a una complejidad excesiva en los entornos debido a distintas plataformas y tecnologías utilizadas en las nubes públicas frente a entornos locales.</span><span class="sxs-lookup"><span data-stu-id="a88d8-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="a88d8-107">Microsoft proporciona la mejor solución de nube híbrida, uno en el que puede optimizar los recursos existentes en el entorno local y en la nube pública, mientras que garantizar la coherencia de una nube híbrida de Azure.</span><span class="sxs-lookup"><span data-stu-id="a88d8-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="a88d8-108">Puede maximizar las habilidades existentes y obtener un enfoque flexible y unificado para crear aplicaciones que se pueden ejecutar en la nube o local, gracias a Azure Stack (local) y Azure (nube pública).</span><span class="sxs-lookup"><span data-stu-id="a88d8-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="a88d8-109">En cuanto a seguridad, puede centralizar la administración y seguridad en la nube híbrida.</span><span class="sxs-lookup"><span data-stu-id="a88d8-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="a88d8-110">Puede obtener el control sobre todos los recursos del centro de datos a la nube, proporcionando el inicio de sesión único en el entorno local y aplicaciones en la nube.</span><span class="sxs-lookup"><span data-stu-id="a88d8-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="a88d8-111">Esto se consigue mediante la extensión de Active Directory a una nube híbrida y mediante el uso de administración de identidades.</span><span class="sxs-lookup"><span data-stu-id="a88d8-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="a88d8-112">Por último, puede distribuir y analizar datos sin problemas, use los mismos lenguajes de consulta para los recursos locales y en la nube y aplicar análisis y aprendizaje profundo de Azure para enriquecer los datos, independientemente de su origen.</span><span class="sxs-lookup"><span data-stu-id="a88d8-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="a88d8-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a88d8-113">Azure Stack</span></span>

<span data-ttu-id="a88d8-114">Azure Stack es una plataforma de nube híbrida que le permite proporcionar servicios de Azure desde el centro de datos de su organización.</span><span class="sxs-lookup"><span data-stu-id="a88d8-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="a88d8-115">Azure Stack está diseñado para admitir las nuevas opciones para las aplicaciones modernas en escenarios clave, como borde y entornos desconectados o resolver determinados requisitos de seguridad y cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a88d8-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="a88d8-116">Figura 4-13 se muestra una visión general de la plataforma de nube híbrida verdadera que ofrece Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a88d8-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Plataforma de nube híbrida de Microsoft con Azure Stack y Azure](./media/image13.jpg)

> <span data-ttu-id="a88d8-118">**Figura 4-13.**</span><span class="sxs-lookup"><span data-stu-id="a88d8-118">**Figure 4-13.**</span></span> <span data-ttu-id="a88d8-119">Plataforma de nube híbrida de Microsoft con Azure Stack y Azure</span><span class="sxs-lookup"><span data-stu-id="a88d8-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="a88d8-120">Azure Stack se ofrece en dos opciones de implementación para satisfacer sus necesidades:</span><span class="sxs-lookup"><span data-stu-id="a88d8-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="a88d8-121">Sistemas integrados de Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a88d8-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="a88d8-122">Kit de desarrollo de Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a88d8-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="a88d8-123">Sistemas integrados de Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a88d8-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="a88d8-124">Sistemas de Azure Stack integrado se ofrecen a través de una asociación de asociados de Microsoft y de hardware.</span><span class="sxs-lookup"><span data-stu-id="a88d8-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="a88d8-125">La asociación crea una solución que ofrece innovación paced en la nube que sea equilibrada con simplicidad en la administración.</span><span class="sxs-lookup"><span data-stu-id="a88d8-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="a88d8-126">Dado que Azure Stack se ofrece como un sistema integrado de hardware y software, obtener la cantidad adecuada de flexibilidad y control, al seguir adoptando la innovación de la nube.</span><span class="sxs-lookup"><span data-stu-id="a88d8-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="a88d8-127">Sistemas de Azure Stack integrado oscilar entre 4 a 12 nodos y son compatibles en conjunto con asociados de hardware y Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a88d8-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="a88d8-128">Utilice los sistemas integrados de Azure Stack para implementar nuevos escenarios para las cargas de trabajo de producción.</span><span class="sxs-lookup"><span data-stu-id="a88d8-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="a88d8-129">Kit de desarrollo de Azure Stack</span><span class="sxs-lookup"><span data-stu-id="a88d8-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="a88d8-130">Kit de desarrollo de Microsoft Azure Stack es una implementación de nodo único de Azure Stack, que puede usar para evaluar y conocer Azure Stack.</span><span class="sxs-lookup"><span data-stu-id="a88d8-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="a88d8-131">También puede usar el Kit de desarrollo de Azure Stack como entorno de desarrollo, donde puede desarrollar mediante las API y herramientas que son coherentes con Azure.</span><span class="sxs-lookup"><span data-stu-id="a88d8-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="a88d8-132">El Kit de desarrollo de Azure Stack no está pensado para usarse como un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="a88d8-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="a88d8-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a88d8-133">Additional resources</span></span>

- <span data-ttu-id="a88d8-134">**Nube híbrida de Azure**</span><span class="sxs-lookup"><span data-stu-id="a88d8-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="a88d8-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="a88d8-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="a88d8-136">**Cuentas de servicio de Active Directory para contenedores de Windows**</span><span class="sxs-lookup"><span data-stu-id="a88d8-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="a88d8-137">**Crear un contenedor con compatibilidad con Active Directory**</span><span class="sxs-lookup"><span data-stu-id="a88d8-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="a88d8-138">**Licencias de ventaja híbrida de Azure**</span><span class="sxs-lookup"><span data-stu-id="a88d8-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="a88d8-139">[Anterior](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
>[Siguiente](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a88d8-139">[Previous](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
