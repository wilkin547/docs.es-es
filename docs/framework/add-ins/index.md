---
title: Complementos y extensibilidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d288d321063512f91ad94b417bb1a6bf38c9ef9
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="add-ins-and-extensibility"></a><span data-ttu-id="7d068-102">Complementos y extensibilidad</span><span class="sxs-lookup"><span data-stu-id="7d068-102">Add-ins and Extensibility</span></span>
<a name="top"></a> <span data-ttu-id="7d068-103">Los complementos ofrecen características o servicios extendidos para una aplicación host.</span><span class="sxs-lookup"><span data-stu-id="7d068-103">Add-ins provide extended features or services for a host application.</span></span> <span data-ttu-id="7d068-104">El [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proporciona un modelo de programación que los desarrolladores pueden usar para desarrollar complementos y activarlos en la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="7d068-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a programming model that developers can use to develop add-ins and activate them in their host application.</span></span> <span data-ttu-id="7d068-105">Para ello, el modelo construye una canalización de comunicación entre el host y el complemento.</span><span class="sxs-lookup"><span data-stu-id="7d068-105">The model achieves this by constructing a communication pipeline between the host and the add-in.</span></span> <span data-ttu-id="7d068-106">El modelo se implementa con los tipos de los espacios de nombres <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>y <xref:System.AddIn.Contract> .</span><span class="sxs-lookup"><span data-stu-id="7d068-106">The model is implemented by using the types in the <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>, and <xref:System.AddIn.Contract> namespaces.</span></span>  
  
 <span data-ttu-id="7d068-107">Esta información general contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="7d068-107">This overview contains the following sections:</span></span>  
  
-   [<span data-ttu-id="7d068-108">Modelo de complementos</span><span class="sxs-lookup"><span data-stu-id="7d068-108">Add-in Model</span></span>](#addin_model)  
  
-   [<span data-ttu-id="7d068-109">Distinción entre complementos y hosts</span><span class="sxs-lookup"><span data-stu-id="7d068-109">Distinguishing Between Add-ins and Hosts</span></span>](#distinguishing_between_addins_and_hosts)  
  
-   [<span data-ttu-id="7d068-110">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7d068-110">Related Topics</span></span>](#related_topics)  
  
-   [<span data-ttu-id="7d068-111">Referencia</span><span class="sxs-lookup"><span data-stu-id="7d068-111">Reference</span></span>](#reference)  
  
> [!NOTE]
>  <span data-ttu-id="7d068-112">Puede encontrar código de ejemplo adicional y vistas previas de la tecnología de cliente de las herramientas que se usan para crear canalizaciones de complementos en el [sitio de Managed Extensibility and Add-In Framework de CodePlex](http://go.microsoft.com/fwlink/?LinkId=121190).</span><span class="sxs-lookup"><span data-stu-id="7d068-112">You can find additional sample code, and customer technology previews of tools for building add-in pipelines, at the [Managed Extensibility and Add-In Framework site on CodePlex](http://go.microsoft.com/fwlink/?LinkId=121190).</span></span>  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a><span data-ttu-id="7d068-113">Modelo de complementos</span><span class="sxs-lookup"><span data-stu-id="7d068-113">Add-in Model</span></span>  
 <span data-ttu-id="7d068-114">El modelo de complementos está formado por una serie de segmentos que constituyen la canalización de complementos (también llamada “canalización de comunicación”), responsable de toda la comunicación entre el complemento y el host.</span><span class="sxs-lookup"><span data-stu-id="7d068-114">The add-in model consists of a series of segments that make up the add-in pipeline (also known as the communication pipeline), that is responsible for all communication between the add-in and the host.</span></span> <span data-ttu-id="7d068-115">La canalización es un modelo de comunicación simétrico de segmentos que intercambian datos entre un complemento y su host.</span><span class="sxs-lookup"><span data-stu-id="7d068-115">The pipeline is a symmetrical communication model of segments that exchange data between an add-in and its host.</span></span> <span data-ttu-id="7d068-116">Al desarrollar estos segmentos entre el host y el complemento, proporciona los niveles de abstracción necesarios para admitir el control de versiones y el aislamiento del complemento.</span><span class="sxs-lookup"><span data-stu-id="7d068-116">Developing these segments between the host and the add-in provides the required layers of abstraction that support versioning and isolation of the add-in.</span></span>  
  
 <span data-ttu-id="7d068-117">La ilustración siguiente muestra la canalización.</span><span class="sxs-lookup"><span data-stu-id="7d068-117">The following illustration shows the pipeline.</span></span>  
  
 <span data-ttu-id="7d068-118">![Agregar &#45; en el modelo de canalización. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span><span class="sxs-lookup"><span data-stu-id="7d068-118">![Add&#45;in pipeline model.](../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span></span>  
<span data-ttu-id="7d068-119">Canalización de complementos</span><span class="sxs-lookup"><span data-stu-id="7d068-119">Add-in pipeline</span></span>  
  
 <span data-ttu-id="7d068-120">No es necesario que los ensamblados de estos segmentos estén en el mismo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d068-120">The assemblies for these segments are not required to be in the same application domain.</span></span> <span data-ttu-id="7d068-121">Puede cargar un complemento en su propio dominio de aplicación nuevo, en un dominio de aplicación existente o, incluso, en el dominio de aplicación del host.</span><span class="sxs-lookup"><span data-stu-id="7d068-121">You can load an add-in into its own new application domain, into an existing application domain, or even into the host's application domain.</span></span> <span data-ttu-id="7d068-122">Puede cargar varios complementos en el mismo dominio de aplicación, lo que permite a los complementos compartir recursos y contextos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7d068-122">You can load multiple add-ins into the same application domain, which enables the add-ins to share resources and security contexts.</span></span>  
  
 <span data-ttu-id="7d068-123">El modelo de complementos admite, y recomienda, un límite opcional entre el host y el complemento, que se denomina “límite de aislamiento” (también llamado “límite de comunicación remota”).</span><span class="sxs-lookup"><span data-stu-id="7d068-123">The add-in model supports, and recommends, an optional boundary between the host and the add-in, which is called the isolation boundary (also known as a remoting boundary).</span></span> <span data-ttu-id="7d068-124">Este límite puede ser un límite de proceso o un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d068-124">This boundary can be an application domain or process boundary.</span></span>  
  
 <span data-ttu-id="7d068-125">El segmento de contrato situado en el centro de la canalización se carga en el dominio de aplicación del host y el dominio de aplicación del complemento.</span><span class="sxs-lookup"><span data-stu-id="7d068-125">The contract segment in the middle of the pipeline is loaded into both the host's application domain and the add-in's application domain.</span></span> <span data-ttu-id="7d068-126">El contrato define los métodos virtuales que utilizan el host y el complemento para intercambiar tipos entre sí.</span><span class="sxs-lookup"><span data-stu-id="7d068-126">The contract defines the virtual methods that the host and the add-in use to exchange types with each other.</span></span>  
  
 <span data-ttu-id="7d068-127">Para pasar a través del límite de aislamiento, los tipos deben ser contratos o tipos serializables.</span><span class="sxs-lookup"><span data-stu-id="7d068-127">To pass through the isolation boundary, types must be either contracts or serializable types.</span></span> <span data-ttu-id="7d068-128">Los segmentos de adaptador de la canalización deben convertir en contratos los tipos que no son contratos ni tipos serializables.</span><span class="sxs-lookup"><span data-stu-id="7d068-128">Types that are not contracts or serializable types must be converted to contracts by the adapter segments in the pipeline.</span></span>  
  
 <span data-ttu-id="7d068-129">Los segmentos de vista de la canalización son interfaces o clases base abstractas que proporcionan al host y al complemento una vista de los métodos que comparten, como se define en el contrato.</span><span class="sxs-lookup"><span data-stu-id="7d068-129">The view segments of the pipeline are abstract base classes or interfaces that provide the host and the add-in with a view of the methods that they share, as defined by the contract.</span></span>  
  
 <span data-ttu-id="7d068-130">Para obtener más información sobre cómo desarrollar segmentos de canalización, consulte [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).</span><span class="sxs-lookup"><span data-stu-id="7d068-130">For more information about developing pipeline segments, see [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).</span></span>  
  
 <span data-ttu-id="7d068-131">Las secciones siguientes describen las características del modelo de complementos.</span><span class="sxs-lookup"><span data-stu-id="7d068-131">The sections that follow describe the features of the add-in model.</span></span>  
  
### <a name="independent-versioning"></a><span data-ttu-id="7d068-132">Control de versiones independiente</span><span class="sxs-lookup"><span data-stu-id="7d068-132">Independent Versioning</span></span>  
 <span data-ttu-id="7d068-133">El modelo de complementos permite controlar de manera independiente las versiones de los hosts y los complementos.</span><span class="sxs-lookup"><span data-stu-id="7d068-133">The add-in model allows hosts and add-ins to version independently.</span></span> <span data-ttu-id="7d068-134">En consecuencia, el modelo de complementos habilita los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d068-134">As a result, the add-in model enables the following scenarios:</span></span>  
  
-   <span data-ttu-id="7d068-135">Creación de un adaptador que permite a un host utilizar un complemento compilado para una versión anterior del host.</span><span class="sxs-lookup"><span data-stu-id="7d068-135">Creating an adapter that enables a host to use an add-in built for a previous version of the host.</span></span>  
  
-   <span data-ttu-id="7d068-136">Creación de un adaptador que permite a un host utilizar un complemento compilado para una versión posterior del host.</span><span class="sxs-lookup"><span data-stu-id="7d068-136">Creating an adapter that enables a host to use an add-in built for a later version of the host.</span></span>  
  
-   <span data-ttu-id="7d068-137">Creación de un adaptador que permite a un host utilizar complementos compilados para otro host.</span><span class="sxs-lookup"><span data-stu-id="7d068-137">Creating an adapter that enables a host to use add-ins built for a different host.</span></span>  
  
### <a name="discovery-and-activation"></a><span data-ttu-id="7d068-138">Detección y activación</span><span class="sxs-lookup"><span data-stu-id="7d068-138">Discovery and Activation</span></span>  
 <span data-ttu-id="7d068-139">Puede activar un complemento con un token de una colección que representa a los complementos encontrados en un almacén de información.</span><span class="sxs-lookup"><span data-stu-id="7d068-139">You can activate an add-in by using a token from a collection that represents the add-ins found from an information store.</span></span> <span data-ttu-id="7d068-140">Los complementos se encuentran buscando el tipo que define la vista del host del complemento.</span><span class="sxs-lookup"><span data-stu-id="7d068-140">Add-ins are found by searching for the type that defines the host's view of the add-in.</span></span> <span data-ttu-id="7d068-141">También puede buscar un complemento específico por el tipo que define al complemento.</span><span class="sxs-lookup"><span data-stu-id="7d068-141">You can also find a specific add-in by the type that defines the add-in.</span></span> <span data-ttu-id="7d068-142">El almacén de información se compone de dos archivos caché: el almacén de canalizaciones y el almacén de complementos.</span><span class="sxs-lookup"><span data-stu-id="7d068-142">The information store consists of two cache files: the pipeline store and the add-in store.</span></span>  
  
 <span data-ttu-id="7d068-143">Para obtener información sobre cómo actualizar y volver a generar el almacén de información, consulte [Add-in Discovery](http://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421).</span><span class="sxs-lookup"><span data-stu-id="7d068-143">For information about updating and rebuilding the information store, see [Add-in Discovery](http://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421).</span></span> <span data-ttu-id="7d068-144">Para obtener información sobre la activación de complementos, consulte [activación de complementos](http://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f) y [Cómo: activar complementos con seguridad y aislamiento diferentes](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span><span class="sxs-lookup"><span data-stu-id="7d068-144">For information about activating add-ins, see [Add-in Activation](http://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f) and [How to: Activate Add-ins with Different Isolation and Security](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="isolation-levels-and-external-processes"></a><span data-ttu-id="7d068-145">Niveles de aislamiento y procesos externos</span><span class="sxs-lookup"><span data-stu-id="7d068-145">Isolation Levels and External Processes</span></span>  
 <span data-ttu-id="7d068-146">El modelo de complementos admite varios niveles de aislamiento entre un complemento y su host o entre diferentes complementos. Empezando por el menos aislado, los niveles son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d068-146">The add-in model supports several levels of isolation between an add-in and its host or between add-ins. Starting from the least isolated, these levels are as follows:</span></span>  
  
-   <span data-ttu-id="7d068-147">El complemento se ejecuta en el mismo dominio de aplicación que el host.</span><span class="sxs-lookup"><span data-stu-id="7d068-147">The add-in runs in the same application domain as the host.</span></span> <span data-ttu-id="7d068-148">No le recomendamos esta opción, porque con ella pierde la funcionalidad de aislamiento y descarga que obtiene al utilizar diferentes dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d068-148">This is not recommended because you lose the isolation and unloading capabilities that you get when you use different application domains.</span></span>  
  
-   <span data-ttu-id="7d068-149">Varios complementos se cargan en el mismo dominio de aplicación, que es diferente del dominio de aplicación que utiliza el host.</span><span class="sxs-lookup"><span data-stu-id="7d068-149">Multiple add-ins are loaded into the same application domain that is different from the application domain used by the host.</span></span>  
  
-   <span data-ttu-id="7d068-150">Cada complemento se carga exclusivamente en su propio dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d068-150">Each add-in is loaded exclusively into its own application domain.</span></span> <span data-ttu-id="7d068-151">Este nivel de aislamiento es el más común.</span><span class="sxs-lookup"><span data-stu-id="7d068-151">This is the most common level of isolation.</span></span>  
  
-   <span data-ttu-id="7d068-152">Varios complementos se cargan en el mismo dominio de aplicación en un proceso externo.</span><span class="sxs-lookup"><span data-stu-id="7d068-152">Multiple add-ins are loaded into the same application domain in an external process.</span></span>  
  
-   <span data-ttu-id="7d068-153">Cada complemento se carga exclusivamente en su propio dominio de aplicación en un proceso externo.</span><span class="sxs-lookup"><span data-stu-id="7d068-153">Each add-in is loaded exclusively into its own application domain in an external process.</span></span> <span data-ttu-id="7d068-154">Este es el escenario más aislado.</span><span class="sxs-lookup"><span data-stu-id="7d068-154">This is the most isolated scenario.</span></span>  
  
 <span data-ttu-id="7d068-155">Para obtener más información sobre el uso de procesos externos, vea [Cómo: activar complementos con seguridad y aislamiento diferentes](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span><span class="sxs-lookup"><span data-stu-id="7d068-155">For more information about using external processes, see [How to: Activate Add-ins with Different Isolation and Security](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="lifetime-management"></a><span data-ttu-id="7d068-156">Administración de la duración</span><span class="sxs-lookup"><span data-stu-id="7d068-156">Lifetime Management</span></span>  
 <span data-ttu-id="7d068-157">Dado que el modelo de complementos abarca los límites de proceso y el dominio de aplicación, la recolección de elementos no utilizados, por sí sola, no es suficiente para liberar y recuperar objetos.</span><span class="sxs-lookup"><span data-stu-id="7d068-157">Because the add-in model spans application domain and process boundaries, garbage collection by itself is not sufficient to release and reclaim objects.</span></span> <span data-ttu-id="7d068-158">El modelo de complementos proporciona un mecanismo de administración del ciclo de vida que utiliza recuentos de referencias y tokens y no suele requerir programación adicional.</span><span class="sxs-lookup"><span data-stu-id="7d068-158">The add-in model provides a lifetime management mechanism that uses tokens and reference counting, and usually does not require additional programming.</span></span> <span data-ttu-id="7d068-159">Para obtener más información, consulte [administración de la duración](http://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="7d068-159">For more information, see [Lifetime Management](http://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
 [<span data-ttu-id="7d068-160">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="7d068-160">Back to top</span></span>](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a><span data-ttu-id="7d068-161">Distinción entre complementos y hosts</span><span class="sxs-lookup"><span data-stu-id="7d068-161">Distinguishing Between Add-ins and Hosts</span></span>  
 <span data-ttu-id="7d068-162">La diferencia entre un complemento y un host consiste, simplemente, en que el host es el que activa el complemento.</span><span class="sxs-lookup"><span data-stu-id="7d068-162">The difference between an add-in and a host is merely that the host is the one that activates the add-in.</span></span> <span data-ttu-id="7d068-163">El host puede ser el mayor de los dos, por ejemplo, una aplicación de procesamiento de texto y sus correctores ortográficos. El host también puede ser el menor de los dos, por ejemplo, un cliente de mensajería instantánea con un reproductor multimedia insertado.</span><span class="sxs-lookup"><span data-stu-id="7d068-163">The host can be the larger of the two, such as a word processing application and its spell checkers; or the host can be the smaller of the two, such as an instant messaging client that embeds a media player.</span></span> <span data-ttu-id="7d068-164">El modelo de complementos admite complementos en escenarios de cliente y de servidor.</span><span class="sxs-lookup"><span data-stu-id="7d068-164">The add-in model supports add-ins in both client and server scenarios.</span></span> <span data-ttu-id="7d068-165">Algunos ejemplos de complementos de servidor son los complementos que proporcionan detección de virus, filtros de correo no deseado y protección de IP a los servidores de correo.</span><span class="sxs-lookup"><span data-stu-id="7d068-165">Examples of server add-ins include add-ins that provide mail servers with virus scanning, spam filters, and IP protection.</span></span> <span data-ttu-id="7d068-166">Ejemplos de complementos de cliente incluyen los complementos de referencia para procesadores de textos, las características especializadas para programas de gráficos y juegos y detección de virus para clientes de correo electrónico local.</span><span class="sxs-lookup"><span data-stu-id="7d068-166">Client add-in examples include reference add-ins for word processors, specialized features for graphics programs and games, and virus scanning for local email clients.</span></span>  
  
 [<span data-ttu-id="7d068-167">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="7d068-167">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="7d068-168">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="7d068-168">Related Topics</span></span>  
  
|<span data-ttu-id="7d068-169">Título</span><span class="sxs-lookup"><span data-stu-id="7d068-169">Title</span></span>|<span data-ttu-id="7d068-170">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d068-170">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7d068-171">Pipeline Development</span><span class="sxs-lookup"><span data-stu-id="7d068-171">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)|<span data-ttu-id="7d068-172">Describe la canalización de comunicación de los segmentos de la aplicación host al complemento.</span><span class="sxs-lookup"><span data-stu-id="7d068-172">Describes the communication pipeline of segments from the host application to the add-in.</span></span> <span data-ttu-id="7d068-173">Proporciona ejemplos de código en los temas del tutorial que describen cómo construir la canalización y cómo implementar segmentos en la canalización de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d068-173">Provides code examples in walkthrough topics that describe how to construct the pipeline and how to deploy segments to the pipeline in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>|  
|[<span data-ttu-id="7d068-174">Dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="7d068-174">Application Domains and Assemblies</span></span>](http://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)|<span data-ttu-id="7d068-175">Describe la relación entre los dominios de aplicación, que proporcionan un límite de aislamiento para la seguridad, la confiabilidad y el control de versiones, además de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="7d068-175">Describes the relationship between application domains, which provide an isolation boundary for security, reliability, and versioning, and assemblies.</span></span>|  
  
 [<span data-ttu-id="7d068-176">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="7d068-176">Back to top</span></span>](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a><span data-ttu-id="7d068-177">Referencia</span><span class="sxs-lookup"><span data-stu-id="7d068-177">Reference</span></span>  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [<span data-ttu-id="7d068-178">Volver al principio</span><span class="sxs-lookup"><span data-stu-id="7d068-178">Back to top</span></span>](#top)