---
title: 'Tutorial: Introducción a las aplicaciones de Windows Communication Foundation'
description: Estos tutoriales se proporciona una introducción para crear aplicaciones de WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 66211cfcf2b742e43eccbefb2bc7c4bd1147b05b
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408865"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a><span data-ttu-id="b4e8e-103">Tutorial: Introducción a las aplicaciones de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b4e8e-103">Tutorial: Get started with Windows Communication Foundation applications</span></span>
<span data-ttu-id="b4e8e-104">La siguiente serie de tutoriales de introducción a la Windows Communication Foundation (WCF) experiencia de programación.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-104">The following series of tutorials introduce you to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="b4e8e-105">Trabajar con estos tutoriales en orden le proporcionará una introducción a los pasos necesarios para crear aplicaciones WCF.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-105">Working through these tutorials in order will give you an introductory understanding of the steps required to create WCF applications.</span></span> <span data-ttu-id="b4e8e-106">Cuando termine, tendrá un servicio WCF y un cliente WCF que llama al servicio.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-106">After you finish, you'll have a running WCF service and a WCF client that calls the service.</span></span> 

<span data-ttu-id="b4e8e-107">El tutorial supone que está utilizando Visual Studio como entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-107">The tutorial assumes you're using Visual Studio as the development environment.</span></span> <span data-ttu-id="b4e8e-108">Si usa otro entorno de desarrollo, omita las instrucciones específico de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-108">If you're using another development environment, ignore the Visual Studio-specific instructions.</span></span> 

<span data-ttu-id="b4e8e-109">Para aplicaciones de WCF de ejemplo que puede descargar y ejecutar, consulte [ejemplos de Windows Communication Foundation](samples/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4e8e-109">For sample WCF applications that you can download and run, see [Windows Communication Foundation samples](samples/index.md).</span></span> <span data-ttu-id="b4e8e-110">Para obtener una introducción a los ejemplos, vea [ejemplo Introducción](samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="b4e8e-110">For an introduction to the samples, see [Getting started sample](samples/getting-started-sample.md).</span></span>

<span data-ttu-id="b4e8e-111">Para obtener información más detallada sobre la creación de servicios y clientes, consulte [programación básica de WCF](basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="b4e8e-111">For more in-depth information about creating services and clients, see [Basic WCF programming](basic-wcf-programming.md).</span></span>

## <a name="wcf-tutorials"></a><span data-ttu-id="b4e8e-112">Tutoriales WCF</span><span class="sxs-lookup"><span data-stu-id="b4e8e-112">WCF tutorials</span></span>

<span data-ttu-id="b4e8e-113">Los tres primeros tutoriales describen cómo definir un contrato de servicio WCF, cómo implementarlo y cómo hospedarlo.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-113">The first three tutorials describe how to define a WCF service contract, how to implement it, and how to host it.</span></span> <span data-ttu-id="b4e8e-114">El servicio que crea está autohospedado en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-114">The service that you create is self-hosted within a console application.</span></span> <span data-ttu-id="b4e8e-115">También puede hospedar servicios en Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="b4e8e-115">You can also host services under Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="b4e8e-116">Para obtener más información, vea [Cómo: Hospedar un servicio WCF en IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="b4e8e-116">For more information, see [How to: Host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="b4e8e-117">Aunque utilizar código para configurar el servicio en el tutorial, también puede [configurar servicios dentro de un archivo de configuración](configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="b4e8e-117">Although you use code to configure the service in the tutorial, you can also [configure services within a configuration file](configuring-services-using-configuration-files.md).</span></span> 

- [<span data-ttu-id="b4e8e-118">Tutorial: Definir un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="b4e8e-118">Tutorial: Define a service contract</span></span>](how-to-define-a-wcf-service-contract.md)

    <span data-ttu-id="b4e8e-119">Crear un contrato de WCF con una interfaz definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-119">You create a WCF contract with a user-defined interface.</span></span> <span data-ttu-id="b4e8e-120">Este contrato define la funcionalidad que expone el servicio.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-120">This contract defines the functionality that the service exposes.</span></span>

- [<span data-ttu-id="b4e8e-121">Tutorial: Implementar un contrato de servicio</span><span class="sxs-lookup"><span data-stu-id="b4e8e-121">Tutorial: Implement a service contract</span></span>](how-to-implement-a-wcf-contract.md)

    <span data-ttu-id="b4e8e-122">Después de definir un contrato, se debe implementar una clase de servicio.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-122">After you define a contract, you must implement it with a service class.</span></span>

- [<span data-ttu-id="b4e8e-123">Tutorial: Hospedar y ejecutar un servicio básico</span><span class="sxs-lookup"><span data-stu-id="b4e8e-123">Tutorial: Host and run a basic service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

    <span data-ttu-id="b4e8e-124">Configurar un punto de conexión para el servicio y hospedar el servicio en una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-124">Configure an endpoint for the service and host the service in a console application.</span></span> <span data-ttu-id="b4e8e-125">Para un servicio se vuelva activo, debe configurarlo y hospedarlo en un entorno de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-125">For a service to become active, you must configure it and host it within a run-time environment.</span></span> <span data-ttu-id="b4e8e-126">Este entorno de tiempo de ejecución crea el servicio y controla su contexto y duración.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-126">This run-time environment creates the service and controls its context and lifetime.</span></span>

<span data-ttu-id="b4e8e-127">Los siguientes dos tutoriales describen cómo crear, configurar y expone el uso de una aplicación cliente para llamar a las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-127">The next two tutorials describe how to create, configure, and use a client application to call the operations the service exposes.</span></span> <span data-ttu-id="b4e8e-128">Los servicios publican metadatos que definen la información que una aplicación cliente necesita para comunicarse con el servicio.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-128">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="b4e8e-129">Visual Studio automatiza el proceso de obtener acceso a estos metadatos y lo usa para construir la aplicación cliente para el servicio.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-129">Visual Studio automates the process of accessing this metadata and uses it to construct the client application for the service.</span></span> <span data-ttu-id="b4e8e-130">Si decide no usar Visual Studio, puede usar el [herramienta de utilidad de metadatos de ServiceModel (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-130">If you decide not to use Visual Studio, you can use the [ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) instead.</span></span>

- [<span data-ttu-id="b4e8e-131">Tutorial: Crear un cliente</span><span class="sxs-lookup"><span data-stu-id="b4e8e-131">Tutorial: Create a client</span></span>](how-to-create-a-wcf-client.md)

    <span data-ttu-id="b4e8e-132">Recuperar metadatos para crear a un proxy de cliente WCF desde un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-132">Retrieve metadata for creating a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="b4e8e-133">Recuperar metadatos mediante Visual Studio para agregar una referencia de servicio o puede usar la herramienta de utilidad de metadatos de ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-133">You retrieve metadata by using Visual Studio to add a service reference or you can use the ServiceModel Metadata Utility tool.</span></span> <span data-ttu-id="b4e8e-134">Especifique el punto de conexión que el cliente utiliza para tener acceso al servicio.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-134">You specify the endpoint that the client uses to access the service.</span></span>

- [<span data-ttu-id="b4e8e-135">Tutorial: Usar un cliente</span><span class="sxs-lookup"><span data-stu-id="b4e8e-135">Tutorial: Use a client</span></span>](how-to-use-a-wcf-client.md)

    <span data-ttu-id="b4e8e-136">Usar al proxy de cliente WCF para llamar a las operaciones de servicio.</span><span class="sxs-lookup"><span data-stu-id="b4e8e-136">Use the WCF client proxy to call the service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="b4e8e-137">Referencia</span><span class="sxs-lookup"><span data-stu-id="b4e8e-137">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a><span data-ttu-id="b4e8e-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4e8e-138">See also</span></span>

- [<span data-ttu-id="b4e8e-139">Información general conceptual</span><span class="sxs-lookup"><span data-stu-id="b4e8e-139">Conceptual overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="b4e8e-140">Guía de la documentación</span><span class="sxs-lookup"><span data-stu-id="b4e8e-140">Guide to the documentation</span></span>](guide-to-the-documentation.md)
- [<span data-ttu-id="b4e8e-141">¿Qué es Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b4e8e-141">What is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="b4e8e-142">Detalles de características WCF</span><span class="sxs-lookup"><span data-stu-id="b4e8e-142">WCF feature details</span></span>](feature-details/index.md)
- [<span data-ttu-id="b4e8e-143">Ciclo de vida de programación básica</span><span class="sxs-lookup"><span data-stu-id="b4e8e-143">Basic programming lifecycle</span></span>](basic-programming-lifecycle.md)
- [<span data-ttu-id="b4e8e-144">Creación de clientes</span><span class="sxs-lookup"><span data-stu-id="b4e8e-144">Building clients</span></span>](building-clients.md)
- [<span data-ttu-id="b4e8e-145">Programación básica de WCF</span><span class="sxs-lookup"><span data-stu-id="b4e8e-145">Basic WCF programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="b4e8e-146">Cómo: Crear un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="b4e8e-146">How to: Create a duplex contract</span></span>](feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="b4e8e-147">Cómo: Servicios de Access con un contrato dúplex</span><span class="sxs-lookup"><span data-stu-id="b4e8e-147">How to: Access services with a duplex contract</span></span>](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="b4e8e-148">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="b4e8e-148">ServiceModel Metadata Utility tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="b4e8e-149">Cómo: Utilice Svcutil.exe para descargar documentos de metadatos</span><span class="sxs-lookup"><span data-stu-id="b4e8e-149">How to: Use Svcutil.exe to download metadata documents</span></span>](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [<span data-ttu-id="b4e8e-150">Cómo: Publicar metadatos para un servicio mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="b4e8e-150">How to: Publish metadata for a service using a configuration file</span></span>](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="b4e8e-151">Utilización de enlaces para configurar servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="b4e8e-151">Using bindings to configure services and clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b4e8e-152">Ejemplo de introducción</span><span class="sxs-lookup"><span data-stu-id="b4e8e-152">Getting started sample</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="b4e8e-153">Ejemplos de Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b4e8e-153">Windows Communication Foundation samples</span></span>](samples/index.md)
- [<span data-ttu-id="b4e8e-154">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="b4e8e-154">Self-Host</span></span>](samples/self-host.md)


