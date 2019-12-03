---
title: 'Mallas de servicio: gRPC para desarrolladores de WCF'
description: Usar una malla de servicio para enrutar y equilibrar las solicitudes a los servicios de gRPC en un clúster de Kubernetes.
ms.date: 09/02/2019
ms.openlocfilehash: cc4855b1ed27e29076e4f13f5c5d3dffa63a6554
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711274"
---
# <a name="service-meshes"></a><span data-ttu-id="6efb7-103">Mallas de servicio</span><span class="sxs-lookup"><span data-stu-id="6efb7-103">Service meshes</span></span>

<span data-ttu-id="6efb7-104">Una malla de servicio es un componente de infraestructura que toma el control de las solicitudes de servicio de enrutamiento dentro de una red.</span><span class="sxs-lookup"><span data-stu-id="6efb7-104">A service mesh is an infrastructure component that takes control of routing service requests within a network.</span></span> <span data-ttu-id="6efb7-105">Las mallas de servicio pueden controlar todo tipo de preocupaciones en el nivel de red dentro de un clúster de Kubernetes, incluidos:</span><span class="sxs-lookup"><span data-stu-id="6efb7-105">Service meshes can handle all kinds of network-level concerns within a Kubernetes cluster, including:</span></span>

- <span data-ttu-id="6efb7-106">Detección de servicios</span><span class="sxs-lookup"><span data-stu-id="6efb7-106">Service discovery</span></span>
- <span data-ttu-id="6efb7-107">Equilibrio de carga</span><span class="sxs-lookup"><span data-stu-id="6efb7-107">Load balancing</span></span>
- <span data-ttu-id="6efb7-108">Tolerancia a errores</span><span class="sxs-lookup"><span data-stu-id="6efb7-108">Fault tolerance</span></span>
- <span data-ttu-id="6efb7-109">Cifrado</span><span class="sxs-lookup"><span data-stu-id="6efb7-109">Encryption</span></span>
- <span data-ttu-id="6efb7-110">Supervisión</span><span class="sxs-lookup"><span data-stu-id="6efb7-110">Monitoring</span></span>

<span data-ttu-id="6efb7-111">Las mallas de servicio de Kubernetes funcionan agregando un contenedor adicional, denominado *proxy sidecar*, a cada POD incluido en la malla.</span><span class="sxs-lookup"><span data-stu-id="6efb7-111">Kubernetes service meshes work by adding an extra container, called a *sidecar proxy*, to each pod included in the mesh.</span></span> <span data-ttu-id="6efb7-112">El proxy asume el control de todas las solicitudes de red entrantes y salientes, lo que permite que la configuración y la administración de las redes sean independientes de los contenedores de la aplicación y, en muchos casos, sin necesidad de realizar cambios en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6efb7-112">The proxy takes over handling all inbound and outbound network requests, allowing configuration and management of networking matters to be kept separate from the application containers and, in many cases, without requiring any changes to the application code.</span></span>

<span data-ttu-id="6efb7-113">Tome el [ejemplo del capítulo anterior](kubernetes.md#test-the-application), donde las solicitudes de gRPC de la aplicación web se enrutaron a una única instancia del servicio gRPC.</span><span class="sxs-lookup"><span data-stu-id="6efb7-113">Take the [previous chapter's example](kubernetes.md#test-the-application), where the gRPC requests from the web application were all routed to a single instance of the gRPC service.</span></span> <span data-ttu-id="6efb7-114">Esto sucede porque el nombre de host del servicio se resuelve en una dirección IP y esa dirección IP se almacena en caché durante la duración de la instancia de `HttpClientHandler`.</span><span class="sxs-lookup"><span data-stu-id="6efb7-114">This happens because the service's hostname is resolved to an IP address, and that IP address is cached for the lifetime of the `HttpClientHandler` instance.</span></span> <span data-ttu-id="6efb7-115">Es posible que se pueda solucionar esto mediante el control manual de las búsquedas de DNS o la creación de varios clientes, pero esto complicaría considerablemente el código de aplicación sin agregar ningún valor empresarial o de cliente.</span><span class="sxs-lookup"><span data-stu-id="6efb7-115">It might be possible to work around this by handling DNS lookups manually or creating multiple clients, but this would complicate the application code considerably without adding any business or customer value.</span></span>

<span data-ttu-id="6efb7-116">Mediante una malla de servicio, las solicitudes del contenedor de la aplicación se envían al proxy sidecar, que puede distribuirlas de forma inteligente en todas las instancias del otro servicio.</span><span class="sxs-lookup"><span data-stu-id="6efb7-116">Using a service mesh, the requests from the application container are sent to the sidecar proxy, which can distribute them intelligently across all instances of the other service.</span></span> <span data-ttu-id="6efb7-117">La malla también puede:</span><span class="sxs-lookup"><span data-stu-id="6efb7-117">The mesh can also:</span></span>

- <span data-ttu-id="6efb7-118">Responda sin problemas a errores de instancias individuales de un servicio.</span><span class="sxs-lookup"><span data-stu-id="6efb7-118">Respond seamlessly to failures of individual instances of a service.</span></span>
- <span data-ttu-id="6efb7-119">Controlar la semántica de reintentos para llamadas erróneas o tiempos de espera</span><span class="sxs-lookup"><span data-stu-id="6efb7-119">Handle retry semantics for failed calls or timeouts</span></span>
- <span data-ttu-id="6efb7-120">Reenruta las solicitudes con error a una instancia alternativa sin volver a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="6efb7-120">Reroute failed requests to an alternate instance without returning to the client application at all.</span></span>

<span data-ttu-id="6efb7-121">En la captura de pantalla siguiente se muestra la aplicación StockWeb que se ejecuta con la malla del servicio Linkerd, sin cambios en el código de la aplicación o incluso en la imagen de Docker que se está usando.</span><span class="sxs-lookup"><span data-stu-id="6efb7-121">The following screenshot shows the StockWeb application running with the Linkerd service mesh, with no changes to the application code, or even the Docker image being used.</span></span> <span data-ttu-id="6efb7-122">El único cambio necesario era la adición de una anotación a la implementación en los archivos YAML para los servicios `stockdata` y `stockweb`.</span><span class="sxs-lookup"><span data-stu-id="6efb7-122">The only change required was the addition of an annotation to the Deployment in the YAML files for the `stockdata` and `stockweb` services.</span></span>

![StockWeb con la malla de servicio](media/service-mesh/stockweb-servicemesh-screenshot.png)

<span data-ttu-id="6efb7-124">Puede ver en la columna servidor que las solicitudes de la aplicación StockWeb se han enrutado a ambas réplicas del servicio StockData, a pesar de que se originan desde una sola instancia de `HttpClient` en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6efb7-124">You can see from the Server column that the requests from the StockWeb application have been routed to both replicas of the StockData service, despite originating from a single `HttpClient` instance in the application code.</span></span> <span data-ttu-id="6efb7-125">De hecho, si revisa el código, verá que todas las solicitudes 100 al servicio StockData se realizan simultáneamente con la misma instancia de `HttpClient`, pero con la malla de servicio, esas solicitudes se equilibrarán en todas las instancias de servicio disponibles.</span><span class="sxs-lookup"><span data-stu-id="6efb7-125">In fact, if you review the code, you'll see that all 100 requests to the StockData service are made simultaneously using the same `HttpClient` instance, yet with the service mesh, those requests will be balanced across however many service instances are available.</span></span>

<span data-ttu-id="6efb7-126">Las mallas de servicio solo se aplican al tráfico dentro de un clúster.</span><span class="sxs-lookup"><span data-stu-id="6efb7-126">Service meshes only apply to traffic within a cluster.</span></span> <span data-ttu-id="6efb7-127">Para clientes externos, vea [el siguiente capítulo, equilibrio de carga](load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="6efb7-127">For external clients, see [the next chapter, Load Balancing](load-balancing.md).</span></span>

## <a name="service-mesh-options"></a><span data-ttu-id="6efb7-128">Opciones de malla de servicio</span><span class="sxs-lookup"><span data-stu-id="6efb7-128">Service mesh options</span></span>

<span data-ttu-id="6efb7-129">Hay tres implementaciones de malla de servicio de uso general que actualmente están disponibles para su uso con Kubernetes: istio, Linkerd y Consul Connect.</span><span class="sxs-lookup"><span data-stu-id="6efb7-129">There are three general-purpose service mesh implementations currently available for use with Kubernetes: Istio, Linkerd, and Consul Connect.</span></span> <span data-ttu-id="6efb7-130">Los tres proporcionan enrutamiento/proxy de solicitud, cifrado de tráfico, resistencia, autenticación de host a host y control de tráfico.</span><span class="sxs-lookup"><span data-stu-id="6efb7-130">All three provide request routing/proxying, traffic encryption, resilience, host-to-host authentication, and traffic control.</span></span>

<span data-ttu-id="6efb7-131">La elección de una malla de servicio depende de varios factores:</span><span class="sxs-lookup"><span data-stu-id="6efb7-131">Choosing a service mesh depends multiple factors:</span></span>

- <span data-ttu-id="6efb7-132">Los requisitos específicos de la organización en relación con los costos, el cumplimiento, los planes de soporte técnico de pago, etc.</span><span class="sxs-lookup"><span data-stu-id="6efb7-132">The organization's specific requirements around costs, compliance, paid support plans, and so on.</span></span>
- <span data-ttu-id="6efb7-133">La naturaleza del clúster, su tamaño, el número de servicios implementados y el volumen de tráfico dentro de la red de clústeres.</span><span class="sxs-lookup"><span data-stu-id="6efb7-133">The nature of the cluster, its size, the number of services deployed, and the volume of traffic within the cluster network.</span></span>
- <span data-ttu-id="6efb7-134">Facilidad de implementación y administración de la malla y su uso con los servicios.</span><span class="sxs-lookup"><span data-stu-id="6efb7-134">Ease of deploying and managing the mesh and using it with services.</span></span>

<span data-ttu-id="6efb7-135">Puede encontrar más información sobre cada malla de servicio en sus respectivos sitios Web.</span><span class="sxs-lookup"><span data-stu-id="6efb7-135">More information on each service mesh is available from their respective websites.</span></span>

- [<span data-ttu-id="6efb7-136">**Istio** -istio.IO</span><span class="sxs-lookup"><span data-stu-id="6efb7-136">**Istio** - istio.io</span></span>](https://istio.io)
- [<span data-ttu-id="6efb7-137">**Linkerd** -linkerd.IO</span><span class="sxs-lookup"><span data-stu-id="6efb7-137">**Linkerd** - linkerd.io</span></span>](https://linkerd.io)
- [<span data-ttu-id="6efb7-138">**Consul** -Consul.IO/Mesh.html</span><span class="sxs-lookup"><span data-stu-id="6efb7-138">**Consul** - consul.io/mesh.html</span></span>](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a><span data-ttu-id="6efb7-139">Ejemplo: agregar Linkerd a una implementación</span><span class="sxs-lookup"><span data-stu-id="6efb7-139">Example: add Linkerd to a deployment</span></span>

<span data-ttu-id="6efb7-140">En este ejemplo, aprenderá a usar la malla de servicio Linkerd con la aplicación *StockKube* de [la sección anterior](kubernetes.md).</span><span class="sxs-lookup"><span data-stu-id="6efb7-140">In this example, you'll learn how to use the Linkerd service mesh with the *StockKube* application from [the previous section](kubernetes.md).</span></span>
<span data-ttu-id="6efb7-141">Para seguir este ejemplo, necesitará [instalar la CLI de Linkerd](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span><span class="sxs-lookup"><span data-stu-id="6efb7-141">To follow this example, you'll need to [install the Linkerd CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span></span> <span data-ttu-id="6efb7-142">Los archivos binarios de Windows se pueden descargar en la sección de versiones de GitHub. Asegúrese de usar la versión **estable** más reciente y no una de las versiones perimetrales.</span><span class="sxs-lookup"><span data-stu-id="6efb7-142">Windows binaries can be downloaded from the GitHub releases section; make sure to use the most recent **stable** release and not one of the edge releases.</span></span>

<span data-ttu-id="6efb7-143">Con la CLI de Linkerd instalada, siga el [*Introducción* instrucciones en el sitio web de Linkerd] para instalar los componentes de Linkerd en el clúster de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="6efb7-143">With the Linkerd CLI installed, follow the [*Getting Started* instructions on the Linkerd web site] to install the Linkerd components on your Kubernetes cluster.</span></span> <span data-ttu-id="6efb7-144">Las instrucciones son directas y la instalación solo debe tardar un par de minutos en una instancia local de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="6efb7-144">The instructions are straight-forward and installation should only take a couple of minutes on a local Kubernetes instance.</span></span>

### <a name="add-linkerd-to-kubernetes-deployments"></a><span data-ttu-id="6efb7-145">Agregar Linkerd a las implementaciones de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="6efb7-145">Add Linkerd to Kubernetes deployments</span></span>

<span data-ttu-id="6efb7-146">La CLI de Linkerd proporciona un comando `inject` para agregar las secciones y propiedades necesarias a los archivos Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="6efb7-146">The Linkerd CLI provides an `inject` command to add the necessary sections and properties to Kubernetes files.</span></span> <span data-ttu-id="6efb7-147">Puede ejecutar el comando y escribir el resultado en un archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="6efb7-147">You can run the command and write the output to a new file.</span></span>

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

<span data-ttu-id="6efb7-148">Puede inspeccionar los nuevos archivos para ver qué cambios se han realizado.</span><span class="sxs-lookup"><span data-stu-id="6efb7-148">You can inspect the new files to see what changes have been made.</span></span> <span data-ttu-id="6efb7-149">En el caso de los objetos de implementación, se agrega una anotación de metadatos para indicar a Linkerd que inserte un contenedor de proxy sidecar en el POD cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="6efb7-149">For Deployment objects, a metadata annotation is added to tell Linkerd to inject a sidecar proxy container into the Pod when it's created.</span></span>

<span data-ttu-id="6efb7-150">También es posible canalizar el resultado del comando `linkerd inject` a `kubectl` directamente.</span><span class="sxs-lookup"><span data-stu-id="6efb7-150">It's also possible to pipe the output of the `linkerd inject` command to `kubectl` directly.</span></span> <span data-ttu-id="6efb7-151">Los siguientes comandos funcionarán en PowerShell o en cualquier Shell de Linux.</span><span class="sxs-lookup"><span data-stu-id="6efb7-151">The following commands will work in PowerShell or any Linux shell.</span></span>

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a><span data-ttu-id="6efb7-152">Inspeccionar los servicios en el panel de Linkerd</span><span class="sxs-lookup"><span data-stu-id="6efb7-152">Inspect services in the Linkerd dashboard</span></span>

<span data-ttu-id="6efb7-153">Inicie el panel de Linkerd mediante la CLI de `linkerd`.</span><span class="sxs-lookup"><span data-stu-id="6efb7-153">Launch the Linkerd dashboard using the `linkerd` CLI.</span></span>

```console
linkerd dashboard
```

<span data-ttu-id="6efb7-154">El panel proporciona información detallada sobre todos los servicios que están conectados a la malla.</span><span class="sxs-lookup"><span data-stu-id="6efb7-154">The dashboard provides detailed information about all services that are connected to the mesh.</span></span>

![Panel de Linkerd que muestra las aplicaciones de StockKube](media/service-mesh/linkerd-screenshot.png)

<span data-ttu-id="6efb7-156">Si aumenta el número de réplicas del servicio StockData gRPC tal como se muestra en el ejemplo siguiente y actualiza la página StockWeb en el explorador, debería ver una combinación de identificadores en la columna servidor, que indica que todas las instancias disponibles atienden las solicitudes. .</span><span class="sxs-lookup"><span data-stu-id="6efb7-156">If you increase the number of replicas of the StockData gRPC service as shown in the following example, and refresh the StockWeb page in the browser, you should see a mix of IDs in the Server column, indicating that requests are being served by all the available instances.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

>[!div class="step-by-step"]
><span data-ttu-id="6efb7-157">[Anterior](kubernetes.md)
>[Siguiente](load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="6efb7-157">[Previous](kubernetes.md)
[Next](load-balancing.md)</span></span>
