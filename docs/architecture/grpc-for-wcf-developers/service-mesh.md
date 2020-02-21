---
title: 'Mallas de servicio: gRPC para desarrolladores de WCF'
description: Usar una malla de servicio para enrutar y equilibrar las solicitudes a los servicios de gRPC en un clúster de Kubernetes.
ms.date: 09/02/2019
ms.openlocfilehash: a29d6893e585c7eb60c847cef0149afeeaebcdab
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503385"
---
# <a name="service-meshes"></a><span data-ttu-id="f2dc6-103">Mallas de servicio</span><span class="sxs-lookup"><span data-stu-id="f2dc6-103">Service meshes</span></span>

<span data-ttu-id="f2dc6-104">Una malla de servicio es un componente de infraestructura que toma el control de las solicitudes de servicio de enrutamiento dentro de una red.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-104">A service mesh is an infrastructure component that takes control of routing service requests within a network.</span></span> <span data-ttu-id="f2dc6-105">Las mallas de servicio pueden controlar todo tipo de preocupaciones en el nivel de red dentro de un clúster de Kubernetes, incluidos:</span><span class="sxs-lookup"><span data-stu-id="f2dc6-105">Service meshes can handle all kinds of network-level concerns within a Kubernetes cluster, including:</span></span>

- <span data-ttu-id="f2dc6-106">Detección de servicios</span><span class="sxs-lookup"><span data-stu-id="f2dc6-106">Service discovery</span></span>
- <span data-ttu-id="f2dc6-107">Equilibrio de carga</span><span class="sxs-lookup"><span data-stu-id="f2dc6-107">Load balancing</span></span>
- <span data-ttu-id="f2dc6-108">Tolerancia a errores</span><span class="sxs-lookup"><span data-stu-id="f2dc6-108">Fault tolerance</span></span>
- <span data-ttu-id="f2dc6-109">Cifrado</span><span class="sxs-lookup"><span data-stu-id="f2dc6-109">Encryption</span></span>
- <span data-ttu-id="f2dc6-110">Supervisión</span><span class="sxs-lookup"><span data-stu-id="f2dc6-110">Monitoring</span></span>

<span data-ttu-id="f2dc6-111">Las mallas de servicio de Kubernetes funcionan agregando un contenedor adicional, denominado *proxy sidecar*, a cada POD incluido en la malla.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-111">Kubernetes service meshes work by adding an extra container, called a *sidecar proxy*, to each pod included in the mesh.</span></span> <span data-ttu-id="f2dc6-112">El proxy asume el control de todas las solicitudes de red entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-112">The proxy takes over handling all inbound and outbound network requests.</span></span> <span data-ttu-id="f2dc6-113">Después, puede mantener la configuración y la administración de las redes con independencia de los contenedores de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-113">You can then keep configuration and management of networking matters separate from the application containers.</span></span> <span data-ttu-id="f2dc6-114">En muchos casos, esta separación no requiere ningún cambio en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-114">In many cases, this separation doesn't require any changes to the application code.</span></span>

<span data-ttu-id="f2dc6-115">En el [ejemplo del capítulo anterior](kubernetes.md#test-the-application), las solicitudes de gRPC de la aplicación web se enrutaron a una única instancia del servicio gRPC.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-115">In the [previous chapter's example](kubernetes.md#test-the-application), the gRPC requests from the web application were all routed to a single instance of the gRPC service.</span></span> <span data-ttu-id="f2dc6-116">Esto sucede porque el nombre de host del servicio se resuelve en una dirección IP y esa dirección IP se almacena en caché durante la duración de la instancia de `HttpClientHandler`.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-116">This happens because the service's host name is resolved to an IP address, and that IP address is cached for the lifetime of the `HttpClientHandler` instance.</span></span> <span data-ttu-id="f2dc6-117">Es posible que se pueda solucionar esto mediante el control manual de las búsquedas de DNS o la creación de varios clientes.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-117">It might be possible to work around this by handling DNS lookups manually or creating multiple clients.</span></span> <span data-ttu-id="f2dc6-118">Sin embargo, esta solución complicaría el código de la aplicación sin agregar ningún valor empresarial o de cliente.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-118">But this workaround would complicate the application code without adding any business or customer value.</span></span>

<span data-ttu-id="f2dc6-119">Cuando se usa una malla de servicio, las solicitudes del contenedor de la aplicación se envían al proxy sidecar.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-119">When you use a service mesh, the requests from the application container are sent to the sidecar proxy.</span></span> <span data-ttu-id="f2dc6-120">Después, el proxy sidecar puede distribuirlos de forma inteligente en todas las instancias del otro servicio.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-120">The sidecar proxy can then distribute them intelligently across all instances of the other service.</span></span> <span data-ttu-id="f2dc6-121">La malla también puede:</span><span class="sxs-lookup"><span data-stu-id="f2dc6-121">The mesh can also:</span></span>

- <span data-ttu-id="f2dc6-122">Responda sin problemas a errores de instancias individuales de un servicio.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-122">Respond seamlessly to failures of individual instances of a service.</span></span>
- <span data-ttu-id="f2dc6-123">Administrar la semántica de reintentos para llamadas o tiempos de espera con error.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-123">Handle retry semantics for failed calls or timeouts.</span></span>
- <span data-ttu-id="f2dc6-124">Reenruta las solicitudes con error a una instancia alternativa sin volver a la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-124">Reroute failed requests to an alternate instance without returning to the client application.</span></span>

<span data-ttu-id="f2dc6-125">En la captura de pantalla siguiente se muestra la aplicación StockWeb que se ejecuta con la malla del servicio Linkerd.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-125">The following screenshot shows the StockWeb application running with the Linkerd service mesh.</span></span> <span data-ttu-id="f2dc6-126">No hay ningún cambio en el código de la aplicación y no se usa la imagen de Docker.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-126">There are no changes to the application code, and the Docker image isn't being used.</span></span> <span data-ttu-id="f2dc6-127">El único cambio necesario era la adición de una anotación a la implementación en los archivos YAML para los servicios `stockdata` y `stockweb`.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-127">The only change required was the addition of an annotation to the deployment in the YAML files for the `stockdata` and `stockweb` services.</span></span>

![StockWeb con la malla de servicio](media/service-mesh/stockweb-servicemesh-screenshot.png)

<span data-ttu-id="f2dc6-129">Puede ver en la columna **servidor** que las solicitudes de la aplicación StockWeb se han enrutado a ambas réplicas del servicio StockData, a pesar de que se originan desde una sola instancia de `HttpClient` en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-129">You can see from the **Server** column that the requests from the StockWeb application have been routed to both replicas of the StockData service, despite originating from a single `HttpClient` instance in the application code.</span></span> <span data-ttu-id="f2dc6-130">De hecho, si revisa el código, verá que todas las solicitudes 100 al servicio StockData se realizan simultáneamente mediante la misma instancia de `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-130">In fact, if you review the code, you'll see that all 100 requests to the StockData service are made simultaneously by using the same `HttpClient` instance.</span></span> <span data-ttu-id="f2dc6-131">Con la malla de servicio, esas solicitudes se equilibrarán a lo largo de todas las instancias de servicio disponibles.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-131">With the service mesh, those requests will be balanced across however many service instances are available.</span></span>

<span data-ttu-id="f2dc6-132">Las mallas de servicio solo se aplican al tráfico dentro de un clúster.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-132">Service meshes apply only to traffic within a cluster.</span></span> <span data-ttu-id="f2dc6-133">Para clientes externos, vea el siguiente capítulo, [equilibrio de carga](load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="f2dc6-133">For external clients, see the next chapter, [Load Balancing](load-balancing.md).</span></span>

## <a name="service-mesh-options"></a><span data-ttu-id="f2dc6-134">Opciones de malla de servicio</span><span class="sxs-lookup"><span data-stu-id="f2dc6-134">Service mesh options</span></span>

<span data-ttu-id="f2dc6-135">Hay tres implementaciones de malla de servicio de uso general disponibles para su uso con Kubernetes: [istio](https://istio.io), [Linkerd](https://linkerd.io)y [Consul Connect](https://consul.io/mesh.html).</span><span class="sxs-lookup"><span data-stu-id="f2dc6-135">Three general-purpose service mesh implementations are currently available for use with Kubernetes: [Istio](https://istio.io), [Linkerd](https://linkerd.io), and [Consul Connect](https://consul.io/mesh.html).</span></span> <span data-ttu-id="f2dc6-136">Los tres proporcionan enrutamiento/proxy de solicitud, cifrado de tráfico, resistencia, autenticación de host a host y control de tráfico.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-136">All three provide request routing/proxying, traffic encryption, resilience, host-to-host authentication, and traffic control.</span></span>

<span data-ttu-id="f2dc6-137">La elección de una malla de servicio depende de varios factores:</span><span class="sxs-lookup"><span data-stu-id="f2dc6-137">Choosing a service mesh depends on multiple factors:</span></span>

- <span data-ttu-id="f2dc6-138">Los requisitos específicos de la organización en relación con los costos, el cumplimiento, los planes de soporte técnico de pago, etc.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-138">The organization's specific requirements around costs, compliance, paid support plans, and so on.</span></span>
- <span data-ttu-id="f2dc6-139">La naturaleza del clúster, su tamaño, el número de servicios implementados y el volumen de tráfico dentro de la red de clústeres.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-139">The nature of the cluster, its size, the number of services deployed, and the volume of traffic within the cluster network.</span></span>
- <span data-ttu-id="f2dc6-140">Facilidad de implementación y administración de la malla y su uso con los servicios.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-140">Ease of deploying and managing the mesh and using it with services.</span></span>

## <a name="example-add-linkerd-to-a-deployment"></a><span data-ttu-id="f2dc6-141">Ejemplo: agregar Linkerd a una implementación</span><span class="sxs-lookup"><span data-stu-id="f2dc6-141">Example: Add Linkerd to a deployment</span></span>

<span data-ttu-id="f2dc6-142">En este ejemplo, aprenderá a usar la malla de servicio Linkerd con la aplicación *StockKube* de [la sección anterior](kubernetes.md).</span><span class="sxs-lookup"><span data-stu-id="f2dc6-142">In this example, you'll learn how to use the Linkerd service mesh with the *StockKube* application from [the previous section](kubernetes.md).</span></span>
<span data-ttu-id="f2dc6-143">Para seguir este ejemplo, necesitará [instalar la CLI de Linkerd](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span><span class="sxs-lookup"><span data-stu-id="f2dc6-143">To follow this example, you'll need to [install the Linkerd CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span></span> <span data-ttu-id="f2dc6-144">Puede descargar los archivos binarios de Windows de la sección en la que se enumeran las versiones de GitHub.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-144">You can download Windows binaries from the section that lists GitHub releases.</span></span> <span data-ttu-id="f2dc6-145">Asegúrese de usar la versión *estable* más reciente y no una de las versiones perimetrales.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-145">Be sure to use the most recent *stable* release and not one of the edge releases.</span></span>

<span data-ttu-id="f2dc6-146">Con la CLI de Linkerd instalada, siga las instrucciones [Introducción](https://linkerd.io/2/getting-started/index.html) para instalar los componentes de Linkerd en el clúster de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-146">With the Linkerd CLI installed, follow the [Getting Started](https://linkerd.io/2/getting-started/index.html) instructions to install the Linkerd components on your Kubernetes cluster.</span></span> <span data-ttu-id="f2dc6-147">Las instrucciones son sencillas y la instalación solo debe tardar un par de minutos en una instancia local de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-147">The instructions are straightforward, and installation should take only a couple of minutes on a local Kubernetes instance.</span></span>

### <a name="add-linkerd-to-kubernetes-deployments"></a><span data-ttu-id="f2dc6-148">Agregar Linkerd a las implementaciones de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f2dc6-148">Add Linkerd to Kubernetes deployments</span></span>

<span data-ttu-id="f2dc6-149">La CLI de Linkerd proporciona un comando `inject` para agregar las secciones y propiedades necesarias a los archivos Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-149">The Linkerd CLI provides an `inject` command to add the necessary sections and properties to Kubernetes files.</span></span> <span data-ttu-id="f2dc6-150">Puede ejecutar el comando y escribir el resultado en un archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-150">You can run the command and write the output to a new file.</span></span>

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

<span data-ttu-id="f2dc6-151">Puede inspeccionar los nuevos archivos para ver qué cambios se han realizado.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-151">You can inspect the new files to see what changes have been made.</span></span> <span data-ttu-id="f2dc6-152">En el caso de los objetos de implementación, se agrega una anotación de metadatos para indicar a Linkerd que inserte un contenedor de proxy sidecar en el POD cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-152">For deployment objects, a metadata annotation is added to tell Linkerd to inject a sidecar proxy container into the pod when it's created.</span></span>

<span data-ttu-id="f2dc6-153">También es posible canalizar el resultado del comando `linkerd inject` a `kubectl` directamente.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-153">It's also possible to pipe the output of the `linkerd inject` command to `kubectl` directly.</span></span> <span data-ttu-id="f2dc6-154">Los siguientes comandos funcionarán en PowerShell o en cualquier Shell de Linux.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-154">The following commands will work in PowerShell or any Linux shell.</span></span>

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a><span data-ttu-id="f2dc6-155">Inspeccionar los servicios en el panel de Linkerd</span><span class="sxs-lookup"><span data-stu-id="f2dc6-155">Inspect services in the Linkerd dashboard</span></span>

<span data-ttu-id="f2dc6-156">Abra el panel de Linkerd mediante la CLI de `linkerd`.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-156">Open the Linkerd dashboard by using the `linkerd` CLI.</span></span>

```console
linkerd dashboard
```

<span data-ttu-id="f2dc6-157">El panel proporciona información detallada sobre todos los servicios que están conectados a la malla.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-157">The dashboard provides detailed information about all services that are connected to the mesh.</span></span>

![Panel de Linkerd que muestra las aplicaciones de StockKube](media/service-mesh/linkerd-screenshot.png)

<span data-ttu-id="f2dc6-159">Si aumenta el número de réplicas del servicio StockData gRPC como se muestra en el ejemplo siguiente y actualiza la página StockWeb en el explorador, debería ver una combinación de identificadores en la columna **servidor** .</span><span class="sxs-lookup"><span data-stu-id="f2dc6-159">If you increase the number of replicas of the StockData gRPC service as shown in the following example, and refresh the StockWeb page in the browser, you should see a mix of IDs in the **Server** column.</span></span> <span data-ttu-id="f2dc6-160">Esta combinación indica que todas las instancias disponibles están atendiendo a las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="f2dc6-160">This mix indicates that all the available instances are serving requests.</span></span>

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
><span data-ttu-id="f2dc6-161">[Anterior](kubernetes.md)
>[Siguiente](load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="f2dc6-161">[Previous](kubernetes.md)
[Next](load-balancing.md)</span></span>
