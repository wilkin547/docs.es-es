---
title: Crear aplicaciones de ASP.NET Core 2.1 implementadas como contenedores de Linux en clústeres de AKS y Kubernetes
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: b03b6fab9dcd53e97c2bc4d7e5c958ca4b931077
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221515"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-akskubernetes-orchestrator"></a><span data-ttu-id="b7879-103">Crear aplicaciones de ASP.NET Core 2.1 implementadas como contenedores de Linux en AKS/Kubernetes orchestrator</span><span class="sxs-lookup"><span data-stu-id="b7879-103">Build ASP.NET Core 2.1 applications deployed as Linux containers into AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="b7879-104">Azure Kubernetes Service (AKS) es Kubernetes orquestaciones servicios administrados de Azure que simplifican la administración e implementación de contenedor.</span><span class="sxs-lookup"><span data-stu-id="b7879-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="b7879-105">Características principales de AKS son:</span><span class="sxs-lookup"><span data-stu-id="b7879-105">AKS main features are:</span></span>

- <span data-ttu-id="b7879-106">Un plano de control hospedado de Azure</span><span class="sxs-lookup"><span data-stu-id="b7879-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="b7879-107">Actualizaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="b7879-107">Automated upgrades</span></span>
- <span data-ttu-id="b7879-108">Autorrecuperación</span><span class="sxs-lookup"><span data-stu-id="b7879-108">Self-healing</span></span>
- <span data-ttu-id="b7879-109">Escalado configurables de usuario</span><span class="sxs-lookup"><span data-stu-id="b7879-109">User configurable scaling</span></span>
- <span data-ttu-id="b7879-110">Una experiencia de usuario más sencilla para desarrolladores y operadores del clúster.</span><span class="sxs-lookup"><span data-stu-id="b7879-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="b7879-111">Los ejemplos siguientes exploración la creación de una aplicación de ASP.NET Core 2.1 se ejecuta en Linux y se implementa en un clúster de AKS en Azure, mientras se realiza el desarrollo con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="b7879-111">The following examples explore the creation of an ASP.NET Core 2.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a><span data-ttu-id="b7879-112">Crear el proyecto de ASP.NET Core 2.1 con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="b7879-112">Creating the ASP.NET Core 2.1 Project using Visual Studio 2017</span></span>

<span data-ttu-id="b7879-113">ASP.NET Core es una plataforma de desarrollo de propósito general mantenida por Microsoft y la Comunidad de .NET en GitHub.</span><span class="sxs-lookup"><span data-stu-id="b7879-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="b7879-114">Es multiplataforma, admite Windows, macOS y Linux y puede usarse en escenarios de dispositivo, nube, IoT e incrustados.</span><span class="sxs-lookup"><span data-stu-id="b7879-114">It is cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="b7879-115">Este ejemplo usa un proyecto simple que se basa basado en una plantilla de API Web de Visual Studio, por lo que no necesita conocimientos adicionales para crear el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b7879-115">This example uses a simple project that's based based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="b7879-116">Solo debe crear el proyecto con una plantilla estándar que incluye todos los elementos para ejecutar un proyecto pequeño con una API de REST, mediante la tecnología de ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="b7879-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.1 technology.</span></span>

![Agregar ventana nuevo proyecto en Visual Studio, seleccione la aplicación Web ASP.NET Core.](media/create-aspnet-core-application.png)

<span data-ttu-id="b7879-118">**Figura 4-36**.</span><span class="sxs-lookup"><span data-stu-id="b7879-118">**Figure 4-36**.</span></span> <span data-ttu-id="b7879-119">Crear aplicación ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b7879-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="b7879-120">Para crear el proyecto de ejemplo, deberá seleccionar **archivo** > **New** > **proyecto** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b7879-120">To create the sample project, you have to select **File** > **New** > **Project** on Visual Studio.</span></span> <span data-ttu-id="b7879-121">Verá una lista de plantillas para varios tipos de proyectos, donde tiene que buscar **Web** > **.NET Core** en el panel izquierdo.</span><span class="sxs-lookup"><span data-stu-id="b7879-121">Then you'll see a list of templates for several types of projects, where you have to look for **Web** > **.NET Core** on the left panel.</span></span> <span data-ttu-id="b7879-122">En este ejemplo seleccione **aplicación Web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="b7879-122">For this example select **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="b7879-123">En el cuadro de diálogo siguiente Asegúrese de que ha seleccionado .NET Core y ASP.NET Core 2.1 como plataforma de destino en el pulldowns superior, tal como se muestra en la figura 4-37 y, a continuación, seleccione la opción de API, para crear una aplicación de ASP.NET Core Web API.</span><span class="sxs-lookup"><span data-stu-id="b7879-123">In the next dialog ensure that you have selected .NET Core and ASP.NET Core 2.1 as the target framework in the top pulldowns, as shown in figure 4-37, and then select the API option, to create an ASP.NET Core Web API application.</span></span>

<span data-ttu-id="b7879-124">El .NET Core 2.1 se incluye en Visual Studio 2017, versión 15.7.0 o superior y es automáticamente instalado y configurado para cuando se selecciona el **desarrollo multiplataforma de .NET Core** carga de trabajo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="b7879-124">The .NET Core 2.1 is included in Visual Studio 2017 version 15.7.0 or higher and is automatically installed and configured for you when you select the **.NET Core cross-platform development** workload during installation.</span></span>

![Diálogo Visual Studio para seleccionar el tipo de una aplicación Web de ASP.NET Core con la opción de API seleccionada.](media/create-web-api-application.png)

<span data-ttu-id="b7879-126">**Figura 4-37**.</span><span class="sxs-lookup"><span data-stu-id="b7879-126">**Figure 4-37**.</span></span> <span data-ttu-id="b7879-127">Tipo de proyecto Web API y seleccione ASP.NET CORE 2.1</span><span class="sxs-lookup"><span data-stu-id="b7879-127">Selecting ASP.NET CORE 2.1 and Web API project type</span></span>

<span data-ttu-id="b7879-128">Si tiene cualquier versión anterior de .NET Core, puede descargar e instalar la versión 2.1 de <https://www.microsoft.com/net/download/core#/sdk>.</span><span class="sxs-lookup"><span data-stu-id="b7879-128">If you have any previous version of .NET Core, you can download and install the 2.1 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="b7879-129">Puede agregar compatibilidad con Docker al crear el proyecto en el paso anterior, o una versión posterior, si es necesario después de iniciar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b7879-129">You can add Docker support when creating the project in the previous step, or later, if the need arises after starting the project.</span></span> <span data-ttu-id="b7879-130">Para agregar la compatibilidad con Docker después de la creación del proyecto, haga doble clic en el archivo de proyecto en el **el Explorador de soluciones** y seleccione **agregar** > **compatibilidad con Docker** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b7879-130">To add the Docker support after the project creation, right-click on the project file in the **Solution Explorer** and select **Add** > **Docker support** on the context menu.</span></span>

![Opción del menú contextual para agregar compatibilidad con Docker a un proyecto existente: Haga clic con el botón derecho (en el proyecto) > Agregar > compatibilidad con Docker.](media/add-docker-support-to-project.png)

<span data-ttu-id="b7879-132">**Figura 4-38**.</span><span class="sxs-lookup"><span data-stu-id="b7879-132">**Figure 4-38**.</span></span> <span data-ttu-id="b7879-133">Agregar compatibilidad con Docker al proyecto existente</span><span class="sxs-lookup"><span data-stu-id="b7879-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="b7879-134">Para completar la adición de compatibilidad con Docker, tiene la opción de Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="b7879-134">To complete adding Docker support, you have the choice of Windows or Linux.</span></span> <span data-ttu-id="b7879-135">En este caso, seleccione **Linux**, ya que AKS no es compatible con contenedores de Windows (como los finales de 2018).</span><span class="sxs-lookup"><span data-stu-id="b7879-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Cuadro de diálogo para seleccionar el SO de destino para el archivo Dockerfile.](media/select-linux-docker-support.png)

<span data-ttu-id="b7879-137">**Figura 4-39**.</span><span class="sxs-lookup"><span data-stu-id="b7879-137">**Figure 4-39**.</span></span> <span data-ttu-id="b7879-138">Seleccionar contenedores de Linux.</span><span class="sxs-lookup"><span data-stu-id="b7879-138">Selecting Linux containers.</span></span>

<span data-ttu-id="b7879-139">Con estos sencillos pasos, tendrá la aplicación de ASP.NET Core 2.1, que se ejecuta en un contenedor de Linux.</span><span class="sxs-lookup"><span data-stu-id="b7879-139">With these simple steps, you will have your ASP.NET Core 2.1 application running on a Linux container.</span></span>

<span data-ttu-id="b7879-140">Como puede ver, la integración entre Visual Studio 2017 y Docker está totalmente orientada a la productividad del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="b7879-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="b7879-141">Ahora puede presionar **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b7879-141">Now you can press **F5** to build and run your application.</span></span>

<span data-ttu-id="b7879-142">Después de ejecutar el proyecto, puede enumerar las imágenes mediante la `docker images` comando.</span><span class="sxs-lookup"><span data-stu-id="b7879-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="b7879-143">Debería ver el `mssampleapplication` imagen creada con la implementación automática de nuestro proyecto de Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="b7879-143">You should see the `mssampleapplication` image created with the automatic deploy of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Salida del comando de imágenes de docker, se muestra una lista con la consola: Repositorio, etiqueta, identificador de la imagen, Created (fecha) y tamaño.](media/docker-images-command.png)

<span data-ttu-id="b7879-145">**Figura 4-40**.</span><span class="sxs-lookup"><span data-stu-id="b7879-145">**Figure 4-40**.</span></span> <span data-ttu-id="b7879-146">Vista de imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="b7879-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="b7879-147">Registre la solución en Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="b7879-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="b7879-148">Cargar la imagen en cualquier registro de Docker, como [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) o Docker Hub para las imágenes se puedan implementar en el clúster de AKS desde ese registro.</span><span class="sxs-lookup"><span data-stu-id="b7879-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="b7879-149">En este caso, nos estamos cargando la imagen en Azure Container Registry.</span><span class="sxs-lookup"><span data-stu-id="b7879-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="b7879-150">Crear la imagen en modo de lanzamiento</span><span class="sxs-lookup"><span data-stu-id="b7879-150">Create the image in Release mode</span></span>

<span data-ttu-id="b7879-151">Crear la imagen en **versión** modo (listo para producción) cambiar a la versión como se muestra aquí y presione F5 para ejecutar la aplicación de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b7879-151">Create the image in **Release** Mode (ready for production) changing to Release as shown here and press F5 to run the application again.</span></span>

![Opción de barra de herramientas en Visual Studio para compilar en modo de lanzamiento.](media/select-release-mode.png)

<span data-ttu-id="b7879-153">**Figura 4-41**.</span><span class="sxs-lookup"><span data-stu-id="b7879-153">**Figure 4-41**.</span></span> <span data-ttu-id="b7879-154">Seleccionar modo de versión</span><span class="sxs-lookup"><span data-stu-id="b7879-154">Selecting Release Mode</span></span>

<span data-ttu-id="b7879-155">Si ejecuta el `docker image` comando, verá ambas imágenes creadas.</span><span class="sxs-lookup"><span data-stu-id="b7879-155">If you execute the `docker image` command, you'll see both images created.</span></span> <span data-ttu-id="b7879-156">Uno para `debug` y otro para `release` modo.</span><span class="sxs-lookup"><span data-stu-id="b7879-156">One for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="b7879-157">Crear una nueva etiqueta para la imagen</span><span class="sxs-lookup"><span data-stu-id="b7879-157">Create a new Tag for the Image</span></span>

<span data-ttu-id="b7879-158">Cada imagen de contenedor debe estar etiquetada con el `loginServer` nombre del registro.</span><span class="sxs-lookup"><span data-stu-id="b7879-158">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="b7879-159">Esta etiqueta se utiliza para el enrutamiento al insertar imágenes de contenedor en un registro de imágenes.</span><span class="sxs-lookup"><span data-stu-id="b7879-159">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="b7879-160">Puede ver el `loginServer` nombre desde el portal de Azure, teniendo la información de Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="b7879-160">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Vista de explorador del nombre del registro de contenedor de Azure, en la esquina superior derecha.](media/loginServer-name.png)

<span data-ttu-id="b7879-162">**Figura 4-42**.</span><span class="sxs-lookup"><span data-stu-id="b7879-162">**Figure 4-42**.</span></span> <span data-ttu-id="b7879-163">Vista del nombre del registro</span><span class="sxs-lookup"><span data-stu-id="b7879-163">View of the name of the Registry</span></span>

<span data-ttu-id="b7879-164">O bien ejecutando el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b7879-164">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Salida del comando anterior en la consola.](media/az-cli-loginServer-name.png)

<span data-ttu-id="b7879-166">**Figura 4-43**.</span><span class="sxs-lookup"><span data-stu-id="b7879-166">**Figure 4-43**.</span></span> <span data-ttu-id="b7879-167">Obtener el nombre del registro con PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7879-167">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="b7879-168">En ambos casos, deberá obtener el nombre.</span><span class="sxs-lookup"><span data-stu-id="b7879-168">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="b7879-169">En nuestro ejemplo, `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="b7879-169">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="b7879-170">Ahora puede etiquetar la imagen, tomar la última imagen (versión), con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b7879-170">Now you can tag the image, taking the latest image (Release image), with the following command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="b7879-171">Después de ejecutar el `docker tag` de comandos, enumerar las imágenes con el `docker images` comando.</span><span class="sxs-lookup"><span data-stu-id="b7879-171">After running the `docker tag` command, list the images with the `docker images` command.</span></span> <span data-ttu-id="b7879-172">Debería ver la imagen con la nueva etiqueta.</span><span class="sxs-lookup"><span data-stu-id="b7879-172">You should see the image with the new tag.</span></span>

![Salida del comando de imágenes de docker en la consola.](media/tagged-docker-images-list.png)

<span data-ttu-id="b7879-174">**Figura 4-44**.</span><span class="sxs-lookup"><span data-stu-id="b7879-174">**Figure 4-44**.</span></span> <span data-ttu-id="b7879-175">Vista de las imágenes etiquetadas</span><span class="sxs-lookup"><span data-stu-id="b7879-175">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="b7879-176">Insertar la imagen en el ACR de Azure</span><span class="sxs-lookup"><span data-stu-id="b7879-176">Push the image into the Azure ACR</span></span>

<span data-ttu-id="b7879-177">Inserte la imagen en el ACR de Azure, mediante el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="b7879-177">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="b7879-178">Este comando tarda unos minutos, pero proporciona comentarios en el proceso de carga de imágenes.</span><span class="sxs-lookup"><span data-stu-id="b7879-178">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Salida del comando de inserción de docker de la consola: muestra una barra de progreso basada en caracteres para cada capa.](media/uploading-image-to-acr.png)

<span data-ttu-id="b7879-180">**Figura 4-45**.</span><span class="sxs-lookup"><span data-stu-id="b7879-180">**Figure 4-45**.</span></span> <span data-ttu-id="b7879-181">Cargar la imagen en ACR</span><span class="sxs-lookup"><span data-stu-id="b7879-181">Uploading the image to the ACR</span></span>

<span data-ttu-id="b7879-182">Puede ver a continuación el resultado que debería obtener cuando se complete el proceso:</span><span class="sxs-lookup"><span data-stu-id="b7879-182">You can see below the result you should get when the process completes:</span></span>

![Salida del comando de inserción de docker ha terminado, que muestra todas las capas o nodos en la consola.](media/uploading-docker-images-complete.png)

<span data-ttu-id="b7879-184">**Figura 4-46**.</span><span class="sxs-lookup"><span data-stu-id="b7879-184">**Figure 4-46**.</span></span> <span data-ttu-id="b7879-185">Vista de nodos</span><span class="sxs-lookup"><span data-stu-id="b7879-185">View of nodes</span></span>

<span data-ttu-id="b7879-186">El siguiente paso es implementar el contenedor en el clúster de Kubernetes de AKS.</span><span class="sxs-lookup"><span data-stu-id="b7879-186">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="b7879-187">Para que se necesita un archivo (**.yml implementar el archivo**) que, en este caso, contiene:</span><span class="sxs-lookup"><span data-stu-id="b7879-187">For that you need a file (**.yml deploy file**) that, in this case, contains:</span></span>

```yml
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: mssamplesbook
spec:
  replicas: 1
  template:
    metadata:
      labels:
        app: mssample-kub-app
    spec:
      containers:
        - mane: mssample-services-app
          image: mssampleacr.azurecr.io/mssampleaksapplication:v1
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
    name: mssample-kub-app
spec:
  ports:
    - name: http-port
      port: 80
      targetPort: 80
  selector:
    app: mssample-kub-app
  type: LoadBalancer
```

> [!NOTE]
> <span data-ttu-id="b7879-188">Para obtener más información sobre la implementación con Kubernetes, consulte: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="b7879-188">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="b7879-189">Ahora ya está casi listo para implementar mediante **Kubectl**, pero primero debe obtener las credenciales para el clúster de AKS con este comando:</span><span class="sxs-lookup"><span data-stu-id="b7879-189">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Salida del comando anterior en la consola: Combinado MSSampleK8Cluster"como el contexto actual en /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="b7879-191">**Figura 4-47**.</span><span class="sxs-lookup"><span data-stu-id="b7879-191">**Figure 4-47**.</span></span> <span data-ttu-id="b7879-192">obtención de credenciales</span><span class="sxs-lookup"><span data-stu-id="b7879-192">getting credentials</span></span>

<span data-ttu-id="b7879-193">A continuación, utilice el `kubectl create` comando para iniciar la implementación.</span><span class="sxs-lookup"><span data-stu-id="b7879-193">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Salida del comando anterior de la consola: implementación "mssamplesbook" creado.](media/kubectl-create-command.png)

<span data-ttu-id="b7879-196">**Figura 4-48**.</span><span class="sxs-lookup"><span data-stu-id="b7879-196">**Figure 4-48**.</span></span> <span data-ttu-id="b7879-197">Implementar en Kubernetes</span><span class="sxs-lookup"><span data-stu-id="b7879-197">Deploy to Kubernetes</span></span>

<span data-ttu-id="b7879-198">Cuando se completa la implementación, puede tener acceso a la consola de Kubernetes con un proxy local que puede tener acceso temporalmente con este comando:</span><span class="sxs-lookup"><span data-stu-id="b7879-198">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="b7879-199">Y el acceso a la dirección url `http://127.0.0.1:8001`.</span><span class="sxs-lookup"><span data-stu-id="b7879-199">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Vista de explorador del panel de Kubernetes, que muestra las implementaciones, Pods, conjuntos de réplicas y los servicios.](media/kubernetes-cluster-information.png)

<span data-ttu-id="b7879-201">**Figura 4-49**.</span><span class="sxs-lookup"><span data-stu-id="b7879-201">**Figure 4-49**.</span></span> <span data-ttu-id="b7879-202">Ver información de clúster de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="b7879-202">View Kubernetes cluster information</span></span>

<span data-ttu-id="b7879-203">Ahora tiene la aplicación implementada en Azure mediante un contenedor de Linux y un clúster de AKS de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="b7879-203">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="b7879-204">Puede tener acceso a la aplicación que vaya a la dirección IP pública del servicio, que se puede obtener desde el portal de Azure.</span><span class="sxs-lookup"><span data-stu-id="b7879-204">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="b7879-205">Puede ver cómo crear el clúster de AKS para este ejemplo en la sección [ **implementar a Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) en esta guía.</span><span class="sxs-lookup"><span data-stu-id="b7879-205">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b7879-206">[Anterior](set-up-windows-containers-with-powershell.md)
>[Siguiente](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="b7879-206">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
