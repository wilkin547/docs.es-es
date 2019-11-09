---
title: Kubernetes-gRPC para desarrolladores de WCF
description: Ejecutar ASP.NET Core gRPC Services en un clúster de Kubernetes.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 819c761a7a55485612b7fb0c8b392971751d8724
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841580"
---
# <a name="kubernetes"></a><span data-ttu-id="acc01-103">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="acc01-103">Kubernetes</span></span>

<span data-ttu-id="acc01-104">Aunque es posible ejecutar contenedores manualmente en hosts de Docker, para sistemas de producción confiables es preferible usar un motor de orquestación de contenedores para administrar varias instancias que se ejecutan en varios servidores de un clúster.</span><span class="sxs-lookup"><span data-stu-id="acc01-104">Although it's possible to run containers manually on Docker hosts, for reliable production systems it's preferable to use a Container Orchestration Engine to manage multiple instances running across several servers in a cluster.</span></span> <span data-ttu-id="acc01-105">Hay varios motores de orquestación de contenedores disponibles, entre los que se incluyen Kubernetes, Docker Swarm y Apache mesos.</span><span class="sxs-lookup"><span data-stu-id="acc01-105">There are various Container Orchestration Engines available, including Kubernetes, Docker Swarm and Apache Mesos.</span></span> <span data-ttu-id="acc01-106">Pero de estos motores, Kubernetes es mucho más usado, por lo que se centrará en este capítulo.</span><span class="sxs-lookup"><span data-stu-id="acc01-106">But of these engines, Kubernetes is far and away the most widely used, so it will be the focus of this chapter.</span></span>

<span data-ttu-id="acc01-107">Kubernetes incluye la siguiente funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="acc01-107">Kubernetes includes the following functionality:</span></span>

- <span data-ttu-id="acc01-108">La **programación** ejecuta contenedores en varios nodos dentro de un clúster, lo que garantiza el uso equilibrado del recurso disponible, el mantenimiento de los contenedores en ejecución si hay interrupciones y el control de las actualizaciones graduales en nuevas versiones de imágenes o nuevas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="acc01-108">**Scheduling** runs containers on multiple nodes within a cluster, ensuring balanced usage of the available resource, keeping containers running if there are outages, and handling rolling updates to new versions of images or new configurations.</span></span>
- <span data-ttu-id="acc01-109">Las **comprobaciones de estado** supervisan los contenedores para garantizar el servicio continuo.</span><span class="sxs-lookup"><span data-stu-id="acc01-109">**Health checks** monitor containers to ensure continued service.</span></span>
- <span data-ttu-id="acc01-110">La **detección de servicios de DNS &** controla el enrutamiento entre los servicios de un clúster.</span><span class="sxs-lookup"><span data-stu-id="acc01-110">**DNS & service discovery** handles routing between services within a cluster.</span></span>
- <span data-ttu-id="acc01-111">La **entrada** expone los servicios seleccionados externamente y, por lo general, proporciona equilibrio de carga entre las instancias de esos servicios.</span><span class="sxs-lookup"><span data-stu-id="acc01-111">**Ingress** exposes selected services externally, and generally provides load-balancing across instances of those services.</span></span>
- <span data-ttu-id="acc01-112">La **Administración de recursos** adjunta recursos externos como el almacenamiento a contenedores.</span><span class="sxs-lookup"><span data-stu-id="acc01-112">**Resource management** attaches external resources such as storage to containers.</span></span>

<span data-ttu-id="acc01-113">En este capítulo se detallará cómo implementar un servicio de ASP.NET Core gRPC y un sitio web que consume el servicio en un clúster de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="acc01-113">This chapter will detail how to deploy an ASP.NET Core gRPC service and a website that consumes the service into a Kubernetes cluster.</span></span> <span data-ttu-id="acc01-114">La aplicación de ejemplo usada está disponible en el repositorio [dotnet-Architecture/GRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) en github.</span><span class="sxs-lookup"><span data-stu-id="acc01-114">The sample application used is available from on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub,</span></span>

## <a name="kubernetes-terminology"></a><span data-ttu-id="acc01-115">Terminología Kubernetes</span><span class="sxs-lookup"><span data-stu-id="acc01-115">Kubernetes terminology</span></span>

<span data-ttu-id="acc01-116">Kubernetes usa *la configuración de estado deseado*: la API se usa para describir objetos como *pods*, *implementaciones* y *servicios*, y el *plano de control* se encarga de implementar el estado deseado en todos los *nodos* de un *clúster*.</span><span class="sxs-lookup"><span data-stu-id="acc01-116">Kubernetes uses *desired state configuration*: the API is used to describe objects such as *Pods*, *Deployments* and *Services*, and the *Control Plane* takes care of implementing the desired state across all the *nodes* in a *cluster*.</span></span> <span data-ttu-id="acc01-117">Un clúster de Kubernetes tiene un nodo *principal* que ejecuta la *API de Kubernetes*, que se puede comunicar mediante programación o mediante la herramienta de línea de comandos `kubectl`.</span><span class="sxs-lookup"><span data-stu-id="acc01-117">A Kubernetes cluster has a *Master* node that runs the *Kubernetes API*, which can be communicated with programmatically or using the `kubectl` command-line tool.</span></span> <span data-ttu-id="acc01-118">`kubectl` puede crear y administrar objetos mediante argumentos de la línea de comandos, pero funciona mejor con archivos YAML que contienen datos de declaración para objetos Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="acc01-118">`kubectl` can create and manage objects using command-line arguments, but works best with YAML files that contain declaration data for Kubernetes objects.</span></span>

### <a name="kubernetes-yaml-files"></a><span data-ttu-id="acc01-119">Archivos YAML Kubernetes</span><span class="sxs-lookup"><span data-stu-id="acc01-119">Kubernetes YAML files</span></span>

<span data-ttu-id="acc01-120">Cada archivo de Kubernetes YAML tendrá al menos tres propiedades de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="acc01-120">Every Kubernetes YAML file will have at least three top-level properties.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

<span data-ttu-id="acc01-121">La propiedad `apiVersion` se usa para especificar a qué versión (y para qué API) está diseñado el archivo.</span><span class="sxs-lookup"><span data-stu-id="acc01-121">The `apiVersion` property is used to specify which version (and which API) the file is intended for.</span></span> <span data-ttu-id="acc01-122">La propiedad `kind` especifica el tipo de objeto que representa el YAML.</span><span class="sxs-lookup"><span data-stu-id="acc01-122">The `kind` property specifies the kind of object the YAML represents.</span></span> <span data-ttu-id="acc01-123">La propiedad `metadata` contiene propiedades de objeto como `name`, `namespace`o `labels`.</span><span class="sxs-lookup"><span data-stu-id="acc01-123">The `metadata` property contains object properties such as `name`, `namespace`, or `labels`.</span></span>

<span data-ttu-id="acc01-124">La mayoría de los archivos de Kubernetes YAML también tendrán una sección `spec` que describe los recursos y la configuración necesarios para crear el objeto.</span><span class="sxs-lookup"><span data-stu-id="acc01-124">Most Kubernetes YAML files will also have a `spec` section that describes the resources and configuration necessary to create the object.</span></span>

### <a name="pods"></a><span data-ttu-id="acc01-125">Pods</span><span class="sxs-lookup"><span data-stu-id="acc01-125">Pods</span></span>

<span data-ttu-id="acc01-126">Los pods son las unidades básicas de ejecución en Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="acc01-126">Pods are the basic units of execution in Kubernetes.</span></span> <span data-ttu-id="acc01-127">Pueden ejecutar varios contenedores, pero también se usan para ejecutar contenedores únicos.</span><span class="sxs-lookup"><span data-stu-id="acc01-127">They can run multiple containers, but are also used to run single containers.</span></span> <span data-ttu-id="acc01-128">El POD también incluye los recursos de almacenamiento requeridos por los contenedores y la dirección IP de red.</span><span class="sxs-lookup"><span data-stu-id="acc01-128">The pod also includes any storage resources required by the container(s), and the network IP address.</span></span>

### <a name="services"></a><span data-ttu-id="acc01-129">Servicios</span><span class="sxs-lookup"><span data-stu-id="acc01-129">Services</span></span>

<span data-ttu-id="acc01-130">Los servicios son metadatos que describen los pods (o conjuntos de pods) y proporcionan una manera de tener acceso a ellos en el clúster, como asignar un nombre de servicio a un conjunto de direcciones IP Pod mediante el servicio DNS del clúster.</span><span class="sxs-lookup"><span data-stu-id="acc01-130">Services are meta-objects that describe pods (or sets of pods) and provide a way to access them within the cluster, such as mapping a service name to a set of pod IP addresses using the cluster DNS service.</span></span>

### <a name="deployments"></a><span data-ttu-id="acc01-131">Implementaciones</span><span class="sxs-lookup"><span data-stu-id="acc01-131">Deployments</span></span>

<span data-ttu-id="acc01-132">Las implementaciones son los objetos de *Estado descritos* para pods.</span><span class="sxs-lookup"><span data-stu-id="acc01-132">Deployments are the *described state* objects for Pods.</span></span> <span data-ttu-id="acc01-133">Si crea un pod manualmente, cuando termine, no se reiniciará.</span><span class="sxs-lookup"><span data-stu-id="acc01-133">If you create a Pod manually, when it terminates it won't be restarted.</span></span> <span data-ttu-id="acc01-134">Las implementaciones se usan para indicar al clúster qué Pod y cuántas réplicas de esos pods deben ejecutarse en el momento actual.</span><span class="sxs-lookup"><span data-stu-id="acc01-134">Deployments are used to tell the cluster which pods, and how many replicas of those pods, should be running at the present time.</span></span>

### <a name="other-objects"></a><span data-ttu-id="acc01-135">Otros objetos</span><span class="sxs-lookup"><span data-stu-id="acc01-135">Other objects</span></span>

<span data-ttu-id="acc01-136">Los pods, los servicios y las implementaciones son solo tres de los tipos de objeto más básicos.</span><span class="sxs-lookup"><span data-stu-id="acc01-136">Pods, Services, and Deployments are just three of the most basic object types.</span></span> <span data-ttu-id="acc01-137">Hay docenas de otros tipos de objetos que se administran mediante un clúster de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="acc01-137">There are dozens of other types of object that are managed by a Kubernetes cluster.</span></span> <span data-ttu-id="acc01-138">Para obtener más información, consulte la documentación de los [conceptos de Kubernetes](https://kubernetes.io/docs/concepts/) .</span><span class="sxs-lookup"><span data-stu-id="acc01-138">For more information, see the [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) documentation.</span></span>

### <a name="namespaces"></a><span data-ttu-id="acc01-139">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="acc01-139">Namespaces</span></span>

<span data-ttu-id="acc01-140">Los clústeres de Kubernetes están diseñados para escalarse a cientos o miles de nodos y ejecutar un número de servicios similar.</span><span class="sxs-lookup"><span data-stu-id="acc01-140">Kubernetes clusters are designed to scale to hundreds or thousands of nodes, and run similar numbers of services.</span></span> <span data-ttu-id="acc01-141">Para evitar conflictos entre los nombres de objeto, los espacios de nombres se usan para agrupar los objetos como parte de las aplicaciones de mayor tamaño.</span><span class="sxs-lookup"><span data-stu-id="acc01-141">To avoid clashes between object names, namespaces are used to group objects together as part of larger applications.</span></span> <span data-ttu-id="acc01-142">Los servicios propios de Kubernetes se ejecutan en un espacio de nombres `default`.</span><span class="sxs-lookup"><span data-stu-id="acc01-142">Kubernetes own services run in a `default` namespace.</span></span> <span data-ttu-id="acc01-143">Todos los objetos de usuario deben crearse en sus propios espacios de nombres para evitar conflictos potenciales con objetos predeterminados u otros inquilinos del clúster.</span><span class="sxs-lookup"><span data-stu-id="acc01-143">All user objects should be created in their own namespaces to avoid potential clashes with default objects or other tenants in the cluster.</span></span>

## <a name="get-started-with-kubernetes"></a><span data-ttu-id="acc01-144">Introducción a Kubernetes</span><span class="sxs-lookup"><span data-stu-id="acc01-144">Get started with Kubernetes</span></span>

<span data-ttu-id="acc01-145">Si está ejecutando Docker Desktop para Windows o macOS, Kubernetes ya está disponible.</span><span class="sxs-lookup"><span data-stu-id="acc01-145">If you're running Docker Desktop for Windows or macOS, Kubernetes is already available.</span></span> <span data-ttu-id="acc01-146">Simplemente habilítelo en la sección Kubernetes de la ventana de configuración.</span><span class="sxs-lookup"><span data-stu-id="acc01-146">Just enable it in the Kubernetes section of the Settings window.</span></span>

![Habilitación de Kubernetes en Docker Desktop](media/kubernetes/enable-kubernetes-docker-desktop.png)

<span data-ttu-id="acc01-148">Para ejecutar un clúster de Kubernetes local en Linux, consulte [minikube](https://github.com/kubernetes/minikube), o [MicroK8s](https://microk8s.io/) si la distribución de Linux admite [instantáneas](https://snapcraft.io/).</span><span class="sxs-lookup"><span data-stu-id="acc01-148">To run a local Kubernetes cluster in Linux, look at [minikube](https://github.com/kubernetes/minikube), or [MicroK8s](https://microk8s.io/) if your Linux distribution supports [snaps](https://snapcraft.io/).</span></span>

<span data-ttu-id="acc01-149">Para comprobar que el clúster se está ejecutando y es accesible, ejecute el comando `kubectl version`.</span><span class="sxs-lookup"><span data-stu-id="acc01-149">To check that your cluster is running and accessible, run the `kubectl version` command.</span></span>

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

<span data-ttu-id="acc01-150">En este ejemplo, tanto la CLI de `kubectl` como el servidor de Kubernetes ejecutan la versión 1.14.6.</span><span class="sxs-lookup"><span data-stu-id="acc01-150">In this example, both the `kubectl` CLI and the Kubernetes server are running version 1.14.6.</span></span> <span data-ttu-id="acc01-151">Cada versión de `kubectl` se supone que es compatible con la versión anterior y la siguiente del servidor, por lo que `kubectl` 1,14 debe funcionar también con las versiones de servidor 1,13 y 1,15.</span><span class="sxs-lookup"><span data-stu-id="acc01-151">Each version of `kubectl` is supposed to support the previous and next version of the server, so `kubectl` 1.14 should work with server versions 1.13 and 1.15 as well.</span></span>

## <a name="run-services-on-kubernetes"></a><span data-ttu-id="acc01-152">Ejecutar servicios en Kubernetes</span><span class="sxs-lookup"><span data-stu-id="acc01-152">Run services on Kubernetes</span></span>

<span data-ttu-id="acc01-153">La aplicación de ejemplo tiene un directorio `kube` que contiene tres archivos YAML.</span><span class="sxs-lookup"><span data-stu-id="acc01-153">The sample application has a `kube` directory containing three YAML files.</span></span> <span data-ttu-id="acc01-154">El archivo `namespace.yml` declara un espacio de nombres personalizado, `stocks`.</span><span class="sxs-lookup"><span data-stu-id="acc01-154">The `namespace.yml` file declares a custom namespace, `stocks`.</span></span> <span data-ttu-id="acc01-155">El archivo `stockdata.yml` declara la implementación y el servicio de la aplicación gRPC, y el archivo `stockweb.yml` declara la implementación y el servicio para una aplicación Web de ASP.NET Core MVC de 3,0 que consume el servicio gRPC.</span><span class="sxs-lookup"><span data-stu-id="acc01-155">The `stockdata.yml` file declares the Deployment and the Service for the gRPC application, and the `stockweb.yml` file declares the Deployment and Service for an ASP.NET Core 3.0 MVC web application that consumes the gRPC service.</span></span>

<span data-ttu-id="acc01-156">Para usar un archivo `YAML` con `kubectl`, use el comando `apply -f`.</span><span class="sxs-lookup"><span data-stu-id="acc01-156">To use a `YAML` file with `kubectl`, use the `apply -f` command.</span></span>

```console
kubectl apply -f object.yml
```

<span data-ttu-id="acc01-157">El comando `apply` comprobará la validez del archivo YAML y mostrará los errores recibidos de la API, pero no esperará hasta que se hayan creado todos los objetos declarados en el archivo, ya que esto puede tardar algún tiempo.</span><span class="sxs-lookup"><span data-stu-id="acc01-157">The `apply` command will check the validity of the YAML file and display any errors received from the API, but doesn't wait until all the objects declared in the file have been created as this can take some time.</span></span> <span data-ttu-id="acc01-158">Use el comando `kubectl get` con los tipos de objeto pertinentes para comprobar la creación de objetos en el clúster.</span><span class="sxs-lookup"><span data-stu-id="acc01-158">Use the `kubectl get` command with the relevant object types to check on object creation in the cluster.</span></span>

### <a name="the-namespace-declaration"></a><span data-ttu-id="acc01-159">La declaración del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="acc01-159">The namespace declaration</span></span>

<span data-ttu-id="acc01-160">La declaración del espacio de nombres es sencilla y solo requiere la asignación de un `name`.</span><span class="sxs-lookup"><span data-stu-id="acc01-160">Namespace declaration is simple and requires only assigning a `name`.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

<span data-ttu-id="acc01-161">Use `kubectl` para aplicar el archivo de `namespace.yml` y compruebe que el espacio de nombres se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="acc01-161">Use `kubectl` to apply the `namespace.yml` file and check the namespace is created successfully.</span></span>

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a><span data-ttu-id="acc01-162">La aplicación StockData</span><span class="sxs-lookup"><span data-stu-id="acc01-162">The StockData application</span></span>

<span data-ttu-id="acc01-163">El archivo `stockdata.yml` declara dos objetos: una implementación y un servicio.</span><span class="sxs-lookup"><span data-stu-id="acc01-163">The `stockdata.yml` file declares two objects: a Deployment and a Service.</span></span>

#### <a name="the-stockdata-deployment"></a><span data-ttu-id="acc01-164">La implementación de StockData</span><span class="sxs-lookup"><span data-stu-id="acc01-164">The StockData Deployment</span></span>

<span data-ttu-id="acc01-165">La parte de implementación proporciona el `spec` para la propia implementación, incluido el número de réplicas necesario, y un `template` para que la implementación cree y administre los objetos Pod.</span><span class="sxs-lookup"><span data-stu-id="acc01-165">The Deployment part provides the `spec` for the deployment itself, including the number of replicas required, and a `template` for the Pod objects to be created and managed by the deployment.</span></span> <span data-ttu-id="acc01-166">Tenga en cuenta que los objetos de implementación se administran con la API de `apps`, como se especifica en `apiVersion`, en lugar de la API de Kubernetes principal.</span><span class="sxs-lookup"><span data-stu-id="acc01-166">Note that Deployment objects are managed with the `apps` API, as specified in `apiVersion`, rather than the main Kubernetes API.</span></span>

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
  replicas: 1
  template:
    metadata:
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

<span data-ttu-id="acc01-167">La propiedad `spec.selector` se usa para hacer coincidir los pods en ejecución con la implementación.</span><span class="sxs-lookup"><span data-stu-id="acc01-167">The `spec.selector` property is used to match running Pods to the Deployment.</span></span> <span data-ttu-id="acc01-168">La propiedad `metadata.labels` del Pod debe coincidir con la propiedad `matchLabels` o se producirá un error en la llamada a la API.</span><span class="sxs-lookup"><span data-stu-id="acc01-168">The Pod's `metadata.labels` property must match the `matchLabels` property or the API call will fail.</span></span>

<span data-ttu-id="acc01-169">La sección `template.spec` declara el contenedor que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="acc01-169">The `template.spec` section declares the container to be run.</span></span> <span data-ttu-id="acc01-170">Al trabajar con un clúster de Kubernetes local, como el proporcionado por Docker Desktop, puede especificar las imágenes que se compilaron localmente, siempre y cuando tengan una etiqueta de versión.</span><span class="sxs-lookup"><span data-stu-id="acc01-170">When working with a local Kubernetes cluster, such as the one provided by Docker Desktop, you can specify images that were built locally as long as they have a version tag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="acc01-171">De forma predeterminada, Kubernetes siempre buscará e intentará extraer una nueva imagen.</span><span class="sxs-lookup"><span data-stu-id="acc01-171">By default, Kubernetes will always check for and try to pull a new image.</span></span> <span data-ttu-id="acc01-172">Si no puede encontrar la imagen en ninguno de sus repositorios conocidos, se producirá un error en la creación del Pod.</span><span class="sxs-lookup"><span data-stu-id="acc01-172">If it can't find the image in any of its known repositories, the Pod creation will fail.</span></span> <span data-ttu-id="acc01-173">Para trabajar con imágenes locales, establezca el `imagePullPolicy` en `Never`.</span><span class="sxs-lookup"><span data-stu-id="acc01-173">To work with local images, set the `imagePullPolicy` to `Never`.</span></span>

<span data-ttu-id="acc01-174">La propiedad `ports` especifica qué puertos de contenedor deben publicarse en el POD.</span><span class="sxs-lookup"><span data-stu-id="acc01-174">The `ports` property specifies which container ports should be published on the Pod.</span></span>  <span data-ttu-id="acc01-175">La imagen `stockservice` ejecuta el servicio en el puerto HTTP estándar, por lo que se publica el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="acc01-175">The `stockservice` image runs the service on the standard HTTP port, so port 80 is published.</span></span>

<span data-ttu-id="acc01-176">En la sección `resources` se aplican los límites de recursos al contenedor que se ejecuta en el POD.</span><span class="sxs-lookup"><span data-stu-id="acc01-176">The `resources` section applies resource limits to the container running within the pod.</span></span> <span data-ttu-id="acc01-177">Esta es una práctica recomendada, ya que impide que un pod individual consuma toda la CPU o la memoria disponible en un nodo.</span><span class="sxs-lookup"><span data-stu-id="acc01-177">This is good practice as it prevents an individual pod from consuming all the available CPU or memory on a node.</span></span>

> [!NOTE]
> <span data-ttu-id="acc01-178">ASP.NET Core 3,0 se ha optimizado y optimizado para ejecutarse en contenedores limitados por recursos y el `dotnet/core/aspnet` imagen de Docker establece una variable de entorno para indicar al tiempo de ejecución de `dotnet` que se encuentra en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="acc01-178">ASP.NET Core 3.0 has been optimized and tuned to run in resource-limited containers, and the `dotnet/core/aspnet` Docker image sets an environment variable to tell the `dotnet` runtime that it's in a container.</span></span>

#### <a name="the-stockdata-service"></a><span data-ttu-id="acc01-179">El servicio StockData</span><span class="sxs-lookup"><span data-stu-id="acc01-179">The StockData Service</span></span>

<span data-ttu-id="acc01-180">La parte de servicio del archivo YAML declara el servicio que proporciona acceso a los pods dentro del clúster.</span><span class="sxs-lookup"><span data-stu-id="acc01-180">The Service part of the YAML file declares the service that provides access to the Pods within the cluster.</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

<span data-ttu-id="acc01-181">La especificación de servicio usa la propiedad `selector` para hacer coincidir `Pods`en ejecución; en este caso, busque pods con una etiqueta `run: stockdata`.</span><span class="sxs-lookup"><span data-stu-id="acc01-181">The Service spec uses the `selector` property to match running `Pods`, in this case looking for Pods with a label `run: stockdata`.</span></span> <span data-ttu-id="acc01-182">El servicio con nombre publica el `port` especificado en los pods coincidentes.</span><span class="sxs-lookup"><span data-stu-id="acc01-182">The specified `port` on matching Pods are published by the named service.</span></span> <span data-ttu-id="acc01-183">Otros pods que se ejecutan en el espacio de nombres `stocks` pueden acceder a HTTP en este servicio mediante `http://stockdata` como dirección.</span><span class="sxs-lookup"><span data-stu-id="acc01-183">Other Pods running in the `stocks` namespace can access HTTP on this service using `http://stockdata` as the address.</span></span> <span data-ttu-id="acc01-184">Los pods que se ejecutan en otros espacios de nombres pueden usar el nombre de host `http://stockdata.stocks`.</span><span class="sxs-lookup"><span data-stu-id="acc01-184">Pods running in other namespaces can use the `http://stockdata.stocks` hostname.</span></span> <span data-ttu-id="acc01-185">Puede controlar el acceso al servicio entre espacios de nombres mediante [directivas de red](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span><span class="sxs-lookup"><span data-stu-id="acc01-185">You can control cross-namespace service access using [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span></span>

#### <a name="deploy-the-stockdata-application"></a><span data-ttu-id="acc01-186">Implementación de la aplicación StockData</span><span class="sxs-lookup"><span data-stu-id="acc01-186">Deploy the StockData application</span></span>

<span data-ttu-id="acc01-187">Use `kubectl` para aplicar el archivo de `stockdata.yml` y comprobar que se crearon la implementación y el servicio.</span><span class="sxs-lookup"><span data-stu-id="acc01-187">Use `kubectl` to apply the `stockdata.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a><span data-ttu-id="acc01-188">La aplicación StockWeb</span><span class="sxs-lookup"><span data-stu-id="acc01-188">The StockWeb application</span></span>

<span data-ttu-id="acc01-189">El archivo `stockweb.yml` declara la implementación y el servicio de la aplicación MVC.</span><span class="sxs-lookup"><span data-stu-id="acc01-189">The `stockweb.yml` file declares the Deployment and Service for the MVC application.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a><span data-ttu-id="acc01-190">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="acc01-190">Environment variables</span></span>

<span data-ttu-id="acc01-191">En la sección `env` del objeto de implementación se especifican las variables de entorno que se van a establecer en el contenedor que ejecuta las imágenes de `stockweb:1.0.0`.</span><span class="sxs-lookup"><span data-stu-id="acc01-191">The `env` section of the Deployment object specifies environment variables to be set in the container running the `stockweb:1.0.0` images.</span></span>

<span data-ttu-id="acc01-192">La variable de entorno **`StockData__Address`** se asignará al valor de configuración `StockData:Address` gracias al proveedor de configuración EnvironmentVariables.</span><span class="sxs-lookup"><span data-stu-id="acc01-192">The **`StockData__Address`** environment variable will map to the `StockData:Address` configuration setting thanks to the EnvironmentVariables configuration provider.</span></span> <span data-ttu-id="acc01-193">Esta configuración utiliza un carácter de subrayado doble entre nombres para separar secciones.</span><span class="sxs-lookup"><span data-stu-id="acc01-193">This setting uses double underscores between names to separate sections.</span></span> <span data-ttu-id="acc01-194">La dirección usa el nombre del servicio `stockdata`, que se ejecuta en el mismo espacio de nombres Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="acc01-194">The address uses the service name of the `stockdata` Service, which is running in the same Kubernetes namespace.</span></span>

<span data-ttu-id="acc01-195">La variable de entorno **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** establece un modificador <xref:System.AppContext> que habilita las conexiones http/2 sin cifrar para <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="acc01-195">The **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** environment variable sets an <xref:System.AppContext> switch that enables unencrypted HTTP/2 connections for <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="acc01-196">Esta variable de entorno es equivalente a establecer el modificador en el código tal como se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="acc01-196">This environment variable is the equivalent of setting the switch in code as shown here.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="acc01-197">El uso de una variable de entorno para el modificador significa que la configuración se puede cambiar fácilmente en función del contexto en el que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="acc01-197">Using an environment variable for the switch means the setting can easily be changed depending on the context in which the application is running.</span></span>

#### <a name="service-types"></a><span data-ttu-id="acc01-198">Tipos de servicio</span><span class="sxs-lookup"><span data-stu-id="acc01-198">Service types</span></span>

<span data-ttu-id="acc01-199">Para hacer que la aplicación web sea accesible desde fuera del clúster, se usa la propiedad `type: NodePort`.</span><span class="sxs-lookup"><span data-stu-id="acc01-199">To make the Web application accessible from outside the cluster, the `type: NodePort` property is used.</span></span> <span data-ttu-id="acc01-200">Este tipo de propiedad hace que Kubernetes publique el puerto 80 en el servicio en un puerto arbitrario en los sockets de red externos del clúster.</span><span class="sxs-lookup"><span data-stu-id="acc01-200">This property type causes Kubernetes to publish port 80 on the Service to an arbitrary port on the cluster's external network sockets.</span></span> <span data-ttu-id="acc01-201">El puerto asignado puede encontrarse con el comando `kubectl get service`.</span><span class="sxs-lookup"><span data-stu-id="acc01-201">The port assigned can be found using the `kubectl get service` command.</span></span>

<span data-ttu-id="acc01-202">El servicio `stockdata` no debe ser accesible desde fuera del clúster, por lo que usa el tipo predeterminado, `ClusterIP`.</span><span class="sxs-lookup"><span data-stu-id="acc01-202">The `stockdata` service shouldn't be accessible from outside the cluster, so it used the default type, `ClusterIP`.</span></span>

<span data-ttu-id="acc01-203">Lo más probable es que los sistemas de producción usen un equilibrador de carga integrado para exponer las aplicaciones públicas a los consumidores externos.</span><span class="sxs-lookup"><span data-stu-id="acc01-203">Production systems will most likely use an integrated load-balancer to expose public applications to external consumers.</span></span> <span data-ttu-id="acc01-204">Los servicios expuestos de esta manera deben usar el tipo de `LoadBalancer`.</span><span class="sxs-lookup"><span data-stu-id="acc01-204">Services exposed in this way should use the `LoadBalancer` type.</span></span>

<span data-ttu-id="acc01-205">Para obtener más información sobre los tipos de servicio, consulte la documentación de los [servicios de publicación de Kubernetes](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) .</span><span class="sxs-lookup"><span data-stu-id="acc01-205">For more information on service types, see the [Kubernetes' Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) documentation.</span></span>

#### <a name="deploy-the-stockweb-application"></a><span data-ttu-id="acc01-206">Implementación de la aplicación StockWeb</span><span class="sxs-lookup"><span data-stu-id="acc01-206">Deploy the StockWeb application</span></span>

<span data-ttu-id="acc01-207">Use `kubectl` para aplicar el archivo de `stockweb.yml` y comprobar que se crearon la implementación y el servicio.</span><span class="sxs-lookup"><span data-stu-id="acc01-207">Use `kubectl` to apply the `stockweb.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

<span data-ttu-id="acc01-208">La salida del comando `get service` muestra que el puerto HTTP se ha publicado en el puerto `32564` de la red externa; en el caso de Docker Desktop, será localhost.</span><span class="sxs-lookup"><span data-stu-id="acc01-208">The output from the `get service` command shows that the HTTP port has been published to port `32564` on the external network; for Docker Desktop, this will be localhost.</span></span> <span data-ttu-id="acc01-209">Se puede tener acceso a la aplicación desplazándose a `http://localhost:32564`.</span><span class="sxs-lookup"><span data-stu-id="acc01-209">The application can be accessed by browsing to `http://localhost:32564`.</span></span>

### <a name="testing-the-application"></a><span data-ttu-id="acc01-210">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="acc01-210">Testing the application</span></span>

<span data-ttu-id="acc01-211">La aplicación StockWeb muestra una lista de las existencias NASDAQ que se recuperan de un servicio simple de solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="acc01-211">The StockWeb application displays a list of NASDAQ stocks that are retrieved from a simple request-reply service.</span></span> <span data-ttu-id="acc01-212">Para fines de demostración, cada línea también muestra el identificador único de la instancia de servicio que lo devolvió.</span><span class="sxs-lookup"><span data-stu-id="acc01-212">For demonstration purposes, each line also shows the unique ID of the service instance that returned it.</span></span>

![Captura de pantalla StockWeb](media/kubernetes/stockweb-screenshot.png)

<span data-ttu-id="acc01-214">Si aumentó el número de réplicas del servicio `stockdata`, es posible que el valor del **servidor** cambie de línea a línea, pero de hecho todos los registros 100 siempre se devuelven desde la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="acc01-214">If the number of replicas of the `stockdata` service were increased, you might expect the **Server** value to change from line to line, but in fact all 100 records are always returned from the same instance.</span></span> <span data-ttu-id="acc01-215">Si actualiza la página cada pocos segundos, el identificador del servidor sigue siendo el mismo.</span><span class="sxs-lookup"><span data-stu-id="acc01-215">If you refresh the page every few seconds, the server ID remains the same.</span></span> <span data-ttu-id="acc01-216">¿Por qué ocurre esto?</span><span class="sxs-lookup"><span data-stu-id="acc01-216">Why does this happen?</span></span> <span data-ttu-id="acc01-217">Hay dos factores en juego aquí.</span><span class="sxs-lookup"><span data-stu-id="acc01-217">There are two factors at play here.</span></span>

<span data-ttu-id="acc01-218">En primer lugar, el sistema de detección del servicio Kubernetes usa el equilibrio de carga "Round-Robin" de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="acc01-218">First, the Kubernetes service discovery system uses "round-robin" load-balancing by default.</span></span> <span data-ttu-id="acc01-219">La primera vez que se consulta el servidor DNS, se devolverá la primera dirección IP coincidente para el servicio.</span><span class="sxs-lookup"><span data-stu-id="acc01-219">The first time the DNS server is queried, it will return the first matching IP address for the service.</span></span> <span data-ttu-id="acc01-220">La siguiente vez, la siguiente dirección IP de la lista, y así sucesivamente, hasta el final, en la que se recorre en bucle hasta el inicio.</span><span class="sxs-lookup"><span data-stu-id="acc01-220">The next time, the next IP address in the list, and so on, until the end, at which point it loops back to the start.</span></span>

<span data-ttu-id="acc01-221">En segundo lugar, el `HttpClient` que se usa para el cliente de gRPC de la aplicación StockWeb se crea y administra mediante el [ASP.net Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), y se usa una sola instancia de este cliente para cada llamada a la página.</span><span class="sxs-lookup"><span data-stu-id="acc01-221">Second, the `HttpClient` used for the StockWeb application's gRPC client is created and managed by the [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), and a single instance of this client is used for every call to the page.</span></span> <span data-ttu-id="acc01-222">El cliente solo realiza una búsqueda DNS, de modo que todas las solicitudes se enrutan a la misma dirección IP.</span><span class="sxs-lookup"><span data-stu-id="acc01-222">The client only does one DNS lookup, so all requests are routed to the same IP address.</span></span> <span data-ttu-id="acc01-223">Además, dado que el `HttpClientHandler` se almacena en caché por motivos de rendimiento, varias solicitudes en una sucesión *rápida usarán* la misma dirección IP, hasta que expire la entrada DNS almacenada en caché o se elimine la instancia del controlador por algún motivo.</span><span class="sxs-lookup"><span data-stu-id="acc01-223">Furthermore, because the `HttpClientHandler` is cached for performance reasons, multiple requests in quick succession will *all* use the same IP address, until the cached DNS entry expires or the handler instance is disposed for some reason.</span></span>

<span data-ttu-id="acc01-224">Esto significa que, de forma predeterminada, las solicitudes a un servicio gRPC no se equilibran en todas las instancias de ese servicio del clúster.</span><span class="sxs-lookup"><span data-stu-id="acc01-224">This means that by default requests to a gRPC service aren't balanced across all instances of that service in the cluster.</span></span> <span data-ttu-id="acc01-225">Los distintos consumidores usarán instancias diferentes, pero eso no garantiza una buena distribución de las solicitudes y un uso equilibrado de los recursos.</span><span class="sxs-lookup"><span data-stu-id="acc01-225">Different consumers will use different instances, but that doesn't guarantee a good distribution of requests and a balanced use of resources.</span></span>

<span data-ttu-id="acc01-226">En el siguiente capítulo, [mallas de servicio](service-mesh.md), veremos cómo solucionar este problema.</span><span class="sxs-lookup"><span data-stu-id="acc01-226">The next chapter, [Service Meshes](service-mesh.md), will look at how to address this problem.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="acc01-227">[Anterior](docker.md)
>[Siguiente](service-mesh.md)</span><span class="sxs-lookup"><span data-stu-id="acc01-227">[Previous](docker.md)
[Next](service-mesh.md)</span></span>
