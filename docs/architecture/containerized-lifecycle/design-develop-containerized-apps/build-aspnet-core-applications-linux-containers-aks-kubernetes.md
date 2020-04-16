---
title: Compilación de aplicaciones ASP.NET Core 2.2 implementadas como contenedores de Linux en clústeres de AKS/Kubernetes
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.date: 02/25/2019
ms.openlocfilehash: 83d4d0a60db4bdc112bb35bfbf61c0396646ad31
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989030"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="7fde5-103">Compilación de aplicaciones ASP.NET Core 2.2 implementadas como contenedores de Linux en un orquestador de AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="7fde5-103">Build ASP.NET Core 2.2 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="7fde5-104">Azure Kubernetes Service (AKS) es un servicio de orquestaciones de Kubernetes administrado de Azure que simplifica la implementación y la administración de contenedores.</span><span class="sxs-lookup"><span data-stu-id="7fde5-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="7fde5-105">Estas son las características principales de AKS:</span><span class="sxs-lookup"><span data-stu-id="7fde5-105">AKS main features are:</span></span>

- <span data-ttu-id="7fde5-106">Plano de control hospedado en Azure</span><span class="sxs-lookup"><span data-stu-id="7fde5-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="7fde5-107">Actualizaciones automatizadas</span><span class="sxs-lookup"><span data-stu-id="7fde5-107">Automated upgrades</span></span>
- <span data-ttu-id="7fde5-108">Recuperación automática</span><span class="sxs-lookup"><span data-stu-id="7fde5-108">Self-healing</span></span>
- <span data-ttu-id="7fde5-109">Escalado configurable por el usuario</span><span class="sxs-lookup"><span data-stu-id="7fde5-109">User configurable scaling</span></span>
- <span data-ttu-id="7fde5-110">Experiencia de usuario más sencilla para los desarrolladores y los operadores del clúster</span><span class="sxs-lookup"><span data-stu-id="7fde5-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="7fde5-111">En los ejemplos siguientes se explora la creación de una aplicación ASP.NET Core 2.2 que se ejecuta en Linux y se implementa en un clúster de AKS en Azure, mientras que el desarrollo se realiza con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="7fde5-111">The following examples explore the creation of an ASP.NET Core 2.2 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a><span data-ttu-id="7fde5-112">Creación de un proyecto de ASP.NET Core 2.2 con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7fde5-112">Creating the ASP.NET Core 2.2 Project using Visual Studio 2017</span></span>

<span data-ttu-id="7fde5-113">ASP.NET Core es una plataforma de desarrollo de uso general de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en GitHub.</span><span class="sxs-lookup"><span data-stu-id="7fde5-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="7fde5-114">Es multiplataforma, admite Windows, macOS y Linux y puede usarse en escenarios de dispositivo, nube, IoT e incrustados.</span><span class="sxs-lookup"><span data-stu-id="7fde5-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="7fde5-115">En este ejemplo se usa un proyecto simple que se basa en una plantilla de API web de Visual Studio, por lo que no necesita conocimientos adicionales para crear el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="7fde5-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="7fde5-116">Solo debe crear el proyecto con una plantilla estándar que incluya todos los elementos para ejecutar un proyecto pequeño con una API de REST, mediante la tecnología de ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="7fde5-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.2 technology.</span></span>

![Ventana para agregar nuevo proyecto en Visual Studio, con la aplicación web de ASP.NET Core seleccionada.](media/create-aspnet-core-application.png)

<span data-ttu-id="7fde5-118">**Figura 4-36**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-118">**Figure 4-36**.</span></span> <span data-ttu-id="7fde5-119">Creación de una aplicación ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7fde5-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="7fde5-120">Para crear el proyecto de ejemplo en Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto** y elija el tipo de proyecto **Web** en el panel izquierdo, seguido de **Aplicación web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="7fde5-121">En Visual Studio se muestran las plantillas para proyectos web.</span><span class="sxs-lookup"><span data-stu-id="7fde5-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="7fde5-122">Para nuestro ejemplo, seleccione **API** para crear una aplicación ASP.NET Web API.</span><span class="sxs-lookup"><span data-stu-id="7fde5-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="7fde5-123">Compruebe que ha seleccionado ASP.NET Core 2.2 como marco.</span><span class="sxs-lookup"><span data-stu-id="7fde5-123">Verify that you've selected ASP.NET Core 2.2 as the framework.</span></span> <span data-ttu-id="7fde5-124">.NET Core 2.2 está incluido en la última versión de Visual Studio 2017 y se instala y configura automáticamente al instalar Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="7fde5-124">.NET Core 2.2 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![Cuadro de diálogo de Visual Studio para seleccionar el tipo de aplicación web ASP.NET Core con la opción API seleccionada.](media/create-web-api-application.png)

<span data-ttu-id="7fde5-126">**Figura 4-37**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-126">**Figure 4-37**.</span></span> <span data-ttu-id="7fde5-127">Selección de ASP.NET Core 2.2 y del tipo de proyecto API web</span><span class="sxs-lookup"><span data-stu-id="7fde5-127">Selecting ASP.NET CORE 2.2 and Web API project type</span></span>

<span data-ttu-id="7fde5-128">Si tiene una versión anterior de .NET Core, puede descargar e instalar la versión 2.2 de <https://dotnet.microsoft.com/download>.</span><span class="sxs-lookup"><span data-stu-id="7fde5-128">If you have any previous version of .NET Core, you can download and install the 2.2 version from <https://dotnet.microsoft.com/download>.</span></span>

<span data-ttu-id="7fde5-129">Puede agregar compatibilidad con Docker al crear el proyecto o más adelante, por lo que se puede aplicar Docker al proyecto en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="7fde5-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="7fde5-130">Para agregar compatibilidad con Docker después de crear el proyecto, haga clic con el botón derecho en el nodo del proyecto en el Explorador de soluciones y seleccione **Agregar** > **Compatibilidad con Docker** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="7fde5-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![Opción del menú contextual para agregar compatibilidad con Docker a un proyecto existente: Haga clic con el botón derecho (en el proyecto) > Agregar > Compatibilidad con Docker.](media/add-docker-support-to-project.png)

<span data-ttu-id="7fde5-132">**Figura 4-38**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-132">**Figure 4-38**.</span></span> <span data-ttu-id="7fde5-133">Adición de compatibilidad con Docker a un proyecto existente</span><span class="sxs-lookup"><span data-stu-id="7fde5-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="7fde5-134">Para acabar de agregar compatibilidad con Docker, puede elegir Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="7fde5-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="7fde5-135">En este caso, seleccione **Linux**, ya que AKS no admite contenedores de Windows (a partir de finales de 2018).</span><span class="sxs-lookup"><span data-stu-id="7fde5-135">In this case, select **Linux**, because AKS doesn't support Windows Containers (as of late 2018).</span></span>

![Cuadro de diálogo de opciones para seleccionar el sistema operativo de destino para el archivo Dockerfile.](media/select-linux-docker-support.png)

<span data-ttu-id="7fde5-137">**Figura 4-39**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-137">**Figure 4-39**.</span></span> <span data-ttu-id="7fde5-138">Selección de contenedores de Linux</span><span class="sxs-lookup"><span data-stu-id="7fde5-138">Selecting Linux containers.</span></span>

<span data-ttu-id="7fde5-139">Con estos sencillos pasos, ya tiene la aplicación ASP.NET Core 2.2 en ejecución en un contenedor de Linux.</span><span class="sxs-lookup"><span data-stu-id="7fde5-139">With these simple steps, you have your ASP.NET Core 2.2 application running on a Linux container.</span></span>

<span data-ttu-id="7fde5-140">Como puede ver, la integración entre Visual Studio 2017 y Docker está totalmente orientada a la productividad del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="7fde5-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer's productivity.</span></span>

<span data-ttu-id="7fde5-141">Ahora puede ejecutar la aplicación con la tecla **F5** o el botón **Reproducir**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="7fde5-142">Después de ejecutar el proyecto, puede enumerar las imágenes mediante el comando `docker images`.</span><span class="sxs-lookup"><span data-stu-id="7fde5-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="7fde5-143">Debería ver la imagen `mssampleapplication` creada por la implementación automática de nuestro proyecto con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="7fde5-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Salida de la consola del comando de imágenes de Docker, en la que se muestra una lista con los siguientes elementos: Repositorio, Etiqueta, Id. de imagen, Creado (fecha) y Tamaño.](media/docker-images-command.png)

<span data-ttu-id="7fde5-145">**Figura 4-40**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-145">**Figure 4-40**.</span></span> <span data-ttu-id="7fde5-146">Vista de imágenes de Docker</span><span class="sxs-lookup"><span data-stu-id="7fde5-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="7fde5-147">Registro de la solución en Azure Container Registry</span><span class="sxs-lookup"><span data-stu-id="7fde5-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="7fde5-148">Cargue la imagen en cualquier registro de Docker, como [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) o Docker Hub, para que las imágenes puedan implementarse en el clúster de AKS desde ese registro.</span><span class="sxs-lookup"><span data-stu-id="7fde5-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="7fde5-149">En este caso, vamos a cargar la imagen en Azure Container Registry.</span><span class="sxs-lookup"><span data-stu-id="7fde5-149">In this case, we're uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="7fde5-150">Creación de la imagen en modo de versión</span><span class="sxs-lookup"><span data-stu-id="7fde5-150">Create the image in Release mode</span></span>

<span data-ttu-id="7fde5-151">Ahora vamos a crear la imagen en el modo de **Versión** (listo para producción). Para ello, cambiaremos a **Versión**, como se muestra en la figura 4-41, y ejecutaremos la aplicación como antes.</span><span class="sxs-lookup"><span data-stu-id="7fde5-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![Opción de la barra de herramientas de Visual Studio para compilar en modo de versión.](media/select-release-mode.png)

<span data-ttu-id="7fde5-153">**Figura 4-41**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-153">**Figure 4-41**.</span></span> <span data-ttu-id="7fde5-154">Selección del modo de versión</span><span class="sxs-lookup"><span data-stu-id="7fde5-154">Selecting Release Mode</span></span>

<span data-ttu-id="7fde5-155">Si ejecuta el comando `docker image`, verá que se crean dos imágenes, una para el modo `debug` y otra para el modo `release`.</span><span class="sxs-lookup"><span data-stu-id="7fde5-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="7fde5-156">Creación de una nueva etiqueta para la imagen</span><span class="sxs-lookup"><span data-stu-id="7fde5-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="7fde5-157">Es preciso etiquetar cada imagen de contenedor con el nombre `loginServer` del registro.</span><span class="sxs-lookup"><span data-stu-id="7fde5-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="7fde5-158">Esta etiqueta se usa para el enrutamiento al insertar imágenes de contenedor en un registro de imágenes.</span><span class="sxs-lookup"><span data-stu-id="7fde5-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="7fde5-159">Para ver el nombre `loginServer` desde Azure Portal, tome la información de Azure Container Registry.</span><span class="sxs-lookup"><span data-stu-id="7fde5-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Vista del explorador con el nombre de Azure Container Registry en la esquina superior derecha.](media/loginServer-name.png)

<span data-ttu-id="7fde5-161">**Figura 4-42**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-161">**Figure 4-42**.</span></span> <span data-ttu-id="7fde5-162">Vista del nombre del Registro</span><span class="sxs-lookup"><span data-stu-id="7fde5-162">View of the name of the Registry</span></span>

<span data-ttu-id="7fde5-163">También puede ejecutar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="7fde5-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Salida de la consola del comando anterior.](media/az-cli-loginServer-name.png)

<span data-ttu-id="7fde5-165">**Figura 4-43**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-165">**Figure 4-43**.</span></span> <span data-ttu-id="7fde5-166">Obtención del nombre del registro mediante PowerShell</span><span class="sxs-lookup"><span data-stu-id="7fde5-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="7fde5-167">En ambos casos, obtendrá el nombre.</span><span class="sxs-lookup"><span data-stu-id="7fde5-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="7fde5-168">En nuestro ejemplo, se trata de `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="7fde5-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="7fde5-169">Ahora puede etiquetar la imagen. Para ello, tome la imagen más reciente (la imagen de versión) con este comando:</span><span class="sxs-lookup"><span data-stu-id="7fde5-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="7fde5-170">Después de ejecutar el comando `docker tag`, muestre las imágenes con el comando `docker images`. Debería ver la imagen con la nueva etiqueta.</span><span class="sxs-lookup"><span data-stu-id="7fde5-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Salida de la consola del comando de imágenes de Docker.](media/tagged-docker-images-list.png)

<span data-ttu-id="7fde5-172">**Figura 4-44**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-172">**Figure 4-44**.</span></span> <span data-ttu-id="7fde5-173">Vista de las imágenes etiquetadas</span><span class="sxs-lookup"><span data-stu-id="7fde5-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="7fde5-174">Inserción de la imagen en Azure ACR</span><span class="sxs-lookup"><span data-stu-id="7fde5-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="7fde5-175">Inicie sesión en Azure Container Registry.</span><span class="sxs-lookup"><span data-stu-id="7fde5-175">Log in to the Azure Container Registry</span></span>

```console
az acr login --name mssampleacr
```

<span data-ttu-id="7fde5-176">Inserte la imagen en Azure ACR con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="7fde5-176">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="7fde5-177">Este comando tarda un poco en cargar las imágenes, pero proporciona información durante el proceso.</span><span class="sxs-lookup"><span data-stu-id="7fde5-177">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Salida de la consola del comando de inserción de Docker en la que se muestra una barra de progreso con caracteres para cada capa.](media/uploading-image-to-acr.png)

<span data-ttu-id="7fde5-179">**Figura 4-45**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-179">**Figure 4-45**.</span></span> <span data-ttu-id="7fde5-180">Carga de la imagen en ACR</span><span class="sxs-lookup"><span data-stu-id="7fde5-180">Uploading the image to the ACR</span></span>

<span data-ttu-id="7fde5-181">Puede ver a continuación el resultado que debería obtener cuando se complete el proceso:</span><span class="sxs-lookup"><span data-stu-id="7fde5-181">You can see below the result you should get when the process completes:</span></span>

![Salida de la consola del comando de inserción de Docker una vez finalizado, en la que se muestran todas las capas o nodos.](media/uploading-docker-images-complete.png)

<span data-ttu-id="7fde5-183">**Figura 4-46**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-183">**Figure 4-46**.</span></span> <span data-ttu-id="7fde5-184">Vista de los nodos</span><span class="sxs-lookup"><span data-stu-id="7fde5-184">View of nodes</span></span>

<span data-ttu-id="7fde5-185">El paso siguiente consiste en implementar el contenedor en el clúster de AKS Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="7fde5-185">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="7fde5-186">Para ello, necesita un archivo (un archivo de implementación **.yml**) que contenga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7fde5-186">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

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
        - name: mssample-services-app
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
> <span data-ttu-id="7fde5-187">Para obtener más información sobre la implementación con Kubernetes, vea <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>.</span><span class="sxs-lookup"><span data-stu-id="7fde5-187">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="7fde5-188">Ya está casi listo para realizar la implementación con **Kubectl**, pero primero debe obtener las credenciales para el clúster de AKS con este comando:</span><span class="sxs-lookup"><span data-stu-id="7fde5-188">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Salida de la consola del comando anterior: Merged "MSSampleK8Cluster" as current context in /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="7fde5-190">**Figura 4-47**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-190">**Figure 4-47**.</span></span> <span data-ttu-id="7fde5-191">Obtención de las credenciales</span><span class="sxs-lookup"><span data-stu-id="7fde5-191">getting credentials</span></span>

<span data-ttu-id="7fde5-192">Después, use el comando `kubectl create` para iniciar la implementación.</span><span class="sxs-lookup"><span data-stu-id="7fde5-192">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Salida de la consola del comando anterior: deployment "mssamplesbook" created.](media/kubectl-create-command.png)

<span data-ttu-id="7fde5-195">**Figura 4-48**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-195">**Figure 4-48**.</span></span> <span data-ttu-id="7fde5-196">Implementación en Kubernetes</span><span class="sxs-lookup"><span data-stu-id="7fde5-196">Deploy to Kubernetes</span></span>

<span data-ttu-id="7fde5-197">Una vez completada la implementación, puede acceder a la consola de Kubernetes con un proxy local al que puede acceder temporalmente con este comando:</span><span class="sxs-lookup"><span data-stu-id="7fde5-197">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="7fde5-198">Acceso a la dirección URL `http://127.0.0.1:8001`.</span><span class="sxs-lookup"><span data-stu-id="7fde5-198">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Vista del explorador del panel de Kubernetes, en el que se muestran los elementos Implementaciones, Pods, Conjuntos de réplicas y Servicios.](media/kubernetes-cluster-information.png)

<span data-ttu-id="7fde5-200">**Figura 4-49**.</span><span class="sxs-lookup"><span data-stu-id="7fde5-200">**Figure 4-49**.</span></span> <span data-ttu-id="7fde5-201">Vista de la información del clúster de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="7fde5-201">View Kubernetes cluster information</span></span>

<span data-ttu-id="7fde5-202">Ya tiene la aplicación implementada en Azure mediante un contenedor de Linux y un clúster de AKS Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="7fde5-202">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="7fde5-203">Para acceder a la aplicación, vaya a la dirección IP pública del servicio, que puede obtener en Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="7fde5-203">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="7fde5-204">Si quiere saber cómo se crea el clúster de AKS para este ejemplo, vea la sección [**Implementación en Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) de esta guía.</span><span class="sxs-lookup"><span data-stu-id="7fde5-204">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7fde5-205">[Anterior](set-up-windows-containers-with-powershell.md)
>[Siguiente](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="7fde5-205">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
