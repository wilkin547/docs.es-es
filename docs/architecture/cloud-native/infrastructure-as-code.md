---
title: Infraestructura como código
description: Adopción de infraestructura como código (IaC) con aplicaciones nativas de la nube
ms.date: 05/12/2020
ms.openlocfilehash: 309dd8610ab3b72a6c6da5297f109f822520c5ff
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395347"
---
# <a name="infrastructure-as-code"></a><span data-ttu-id="932d7-103">Infraestructura como código</span><span class="sxs-lookup"><span data-stu-id="932d7-103">Infrastructure as code</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="932d7-104">Los sistemas nativos en la nube adoptan microservicios, contenedores y un diseño moderno del sistema para lograr la velocidad y la agilidad.</span><span class="sxs-lookup"><span data-stu-id="932d7-104">Cloud-native systems embrace microservices, containers, and modern system design to achieve speed and agility.</span></span> <span data-ttu-id="932d7-105">Proporcionan fases automatizadas de compilación y versión para garantizar un código coherente y de calidad.</span><span class="sxs-lookup"><span data-stu-id="932d7-105">They provide automated build and release stages to ensure consistent and quality code.</span></span> <span data-ttu-id="932d7-106">Pero eso es solo parte de la historia.</span><span class="sxs-lookup"><span data-stu-id="932d7-106">But, that's only part of the story.</span></span> <span data-ttu-id="932d7-107">¿Cómo se aprovisionan los entornos de nube en los que se ejecutan estos sistemas?</span><span class="sxs-lookup"><span data-stu-id="932d7-107">How do you provision the cloud environments upon which these systems run?</span></span>

<span data-ttu-id="932d7-108">Las modernas aplicaciones nativas en la nube adoptan la práctica ampliamente aceptada de [infraestructura como código](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), o `IaC` .</span><span class="sxs-lookup"><span data-stu-id="932d7-108">Modern cloud-native applications embrace the widely accepted practice of [Infrastructure as Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), or `IaC`.</span></span>  <span data-ttu-id="932d7-109">Con IaC, puede automatizar el aprovisionamiento de plataforma.</span><span class="sxs-lookup"><span data-stu-id="932d7-109">With IaC, you automate platform provisioning.</span></span> <span data-ttu-id="932d7-110">Esencialmente, aplica prácticas de ingeniería de software, como pruebas y control de versiones a las prácticas de DevOps.</span><span class="sxs-lookup"><span data-stu-id="932d7-110">You essentially apply software engineering practices such as testing and versioning to your DevOps practices.</span></span> <span data-ttu-id="932d7-111">La infraestructura y las implementaciones son automatizadas, coherentes y repetibles.</span><span class="sxs-lookup"><span data-stu-id="932d7-111">Your infrastructure and deployments are automated, consistent, and repeatable.</span></span> <span data-ttu-id="932d7-112">Del mismo modo que la entrega continua automatiza el modelo tradicional de implementaciones manuales, la infraestructura como código (IaC) está evolucionando el modo en que se administran los entornos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="932d7-112">Just as continuous delivery automated the traditional model of manual deployments, Infrastructure as Code (IaC) is evolving how application environments are managed.</span></span>

<span data-ttu-id="932d7-113">Herramientas como Azure Resource Manager (ARM), terraform y la interfaz de la línea de comandos (CLI) de Azure le permiten crear un script de la infraestructura de la nube que necesita mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="932d7-113">Tools like Azure Resource Manager (ARM), Terraform, and the Azure Command Line Interface (CLI) enable you to declaratively script the cloud infrastructure you require.</span></span>

## <a name="azure-resource-manager-templates"></a><span data-ttu-id="932d7-114">Plantillas del Administrador de recursos de Azure</span><span class="sxs-lookup"><span data-stu-id="932d7-114">Azure Resource Manager templates</span></span>

<span data-ttu-id="932d7-115">ARM significa [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/).</span><span class="sxs-lookup"><span data-stu-id="932d7-115">ARM stands for [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/).</span></span> <span data-ttu-id="932d7-116">Es un motor de aprovisionamiento de API que se integra en Azure y se expone como un servicio de API.</span><span class="sxs-lookup"><span data-stu-id="932d7-116">It's an API provisioning engine that is built into Azure and exposed as an API service.</span></span> <span data-ttu-id="932d7-117">ARM permite implementar, actualizar, eliminar y administrar los recursos contenidos en el grupo de recursos de Azure en una única operación coordinada.</span><span class="sxs-lookup"><span data-stu-id="932d7-117">ARM enables you to deploy, update, delete, and manage the resources contained in Azure resource group in a single, coordinated operation.</span></span> <span data-ttu-id="932d7-118">El motor se proporciona con una plantilla basada en JSON que especifica los recursos necesarios y su configuración.</span><span class="sxs-lookup"><span data-stu-id="932d7-118">You provide the engine with a JSON-based template that specifies the resources you require and their configuration.</span></span> <span data-ttu-id="932d7-119">ARM organiza automáticamente la implementación en el orden correcto que respeta las dependencias.</span><span class="sxs-lookup"><span data-stu-id="932d7-119">ARM automatically orchestrates the deployment in the correct order respecting dependencies.</span></span> <span data-ttu-id="932d7-120">El motor de garantiza Idempotencia.</span><span class="sxs-lookup"><span data-stu-id="932d7-120">The engine ensures idempotency.</span></span> <span data-ttu-id="932d7-121">Si ya existe un recurso deseado con la misma configuración, se omitirá el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="932d7-121">If a desired resource already exists with the same configuration, provisioning will be ignored.</span></span>

<span data-ttu-id="932d7-122">Azure Resource Manager plantillas son un lenguaje basado en JSON para definir varios recursos en Azure.</span><span class="sxs-lookup"><span data-stu-id="932d7-122">Azure Resource Manager templates are a JSON-based language for defining various resources in Azure.</span></span> <span data-ttu-id="932d7-123">El esquema básico tiene un aspecto similar al de la figura 10-14.</span><span class="sxs-lookup"><span data-stu-id="932d7-123">The basic schema looks something like Figure 10-14.</span></span>

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
  "contentVersion": "",
  "apiProfile": "",
  "parameters": {  },
  "variables": {  },
  "functions": [  ],
  "resources": [  ],
  "outputs": {  }
}
```

<span data-ttu-id="932d7-124">**Figura 10-14** : el esquema de una plantilla de administrador de recursos</span><span class="sxs-lookup"><span data-stu-id="932d7-124">**Figure 10-14** - The schema for a Resource Manager template</span></span>

<span data-ttu-id="932d7-125">Dentro de esta plantilla, se puede definir un contenedor de almacenamiento dentro de la sección de recursos, como por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="932d7-125">Within this template, one might define a storage container inside the resources section like so:</span></span>

```json
"resources": [
    {
      "type": "Microsoft.Storage/storageAccounts",
      "name": "[variables('storageAccountName')]",
      "location": "[parameters('location')]",
      "apiVersion": "2018-07-01",
      "sku": {
        "name": "[parameters('storageAccountType')]"
      },
      "kind": "StorageV2",
      "properties": {}
    }
  ],
```

<span data-ttu-id="932d7-126">**Figura 10-15** : ejemplo de una cuenta de almacenamiento definida en una plantilla de administrador de recursos</span><span class="sxs-lookup"><span data-stu-id="932d7-126">**Figure 10-15** - An example of a storage account defined in a Resource Manager template</span></span>

<span data-ttu-id="932d7-127">Una plantilla de ARM se puede parametrizar con información de entorno y configuración dinámica.</span><span class="sxs-lookup"><span data-stu-id="932d7-127">An ARM template can be parameterized with dynamic environment and configuration information.</span></span> <span data-ttu-id="932d7-128">De este modo, se puede reutilizar para definir diferentes entornos, como desarrollo, QA o producción.</span><span class="sxs-lookup"><span data-stu-id="932d7-128">Doing so enables it to be reused to define different environments, such as development, QA, or production.</span></span> <span data-ttu-id="932d7-129">Normalmente, la plantilla crea todos los recursos de un único grupo de recursos de Azure.</span><span class="sxs-lookup"><span data-stu-id="932d7-129">Normally, the template creates all resources within a single Azure resource group.</span></span> <span data-ttu-id="932d7-130">Es posible definir varios grupos de recursos en una sola plantilla de Administrador de recursos, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="932d7-130">It's possible to define multiple resource groups in a single Resource Manager template, if needed.</span></span> <span data-ttu-id="932d7-131">Puede eliminar todos los recursos de un entorno eliminando el propio grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="932d7-131">You can delete all resources in an environment by deleting the resource group itself.</span></span> <span data-ttu-id="932d7-132">El análisis de costos también se puede ejecutar en el nivel de grupo de recursos, lo que permite una rápida contabilización de la cantidad de costos de cada entorno.</span><span class="sxs-lookup"><span data-stu-id="932d7-132">Cost analysis can also be run at the resource group level, allowing for quick accounting of how much each environment is costing.</span></span>

<span data-ttu-id="932d7-133">Hay muchos ejemplos o plantillas de ARM disponibles en el proyecto de [plantillas de inicio rápido de Azure](https://github.com/Azure/azure-quickstart-templates) en github.</span><span class="sxs-lookup"><span data-stu-id="932d7-133">There are many examples or ARM templates available in the [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) project on GitHub.</span></span> <span data-ttu-id="932d7-134">Pueden ayudar a acelerar la creación de una nueva plantilla o la modificación de una existente.</span><span class="sxs-lookup"><span data-stu-id="932d7-134">They can help accelerate creating a new template or modifying an existing one.</span></span>

<span data-ttu-id="932d7-135">Administrador de recursos plantillas se pueden ejecutar de muchas maneras.</span><span class="sxs-lookup"><span data-stu-id="932d7-135">Resource Manager templates can be run in many of ways.</span></span> <span data-ttu-id="932d7-136">Quizás la manera más sencilla consiste en pegarlos simplemente en el Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="932d7-136">Perhaps the simplest way is to simply paste them into the Azure portal.</span></span> <span data-ttu-id="932d7-137">En el caso de las implementaciones experimentales, este método puede ser rápido.</span><span class="sxs-lookup"><span data-stu-id="932d7-137">For experimental deployments, this method can be quick.</span></span> <span data-ttu-id="932d7-138">También se pueden ejecutar como parte de un proceso de compilación o lanzamiento en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="932d7-138">They can also be run as part of a build or release process in Azure DevOps.</span></span> <span data-ttu-id="932d7-139">Hay tareas que aprovecharán las conexiones en Azure para ejecutar las plantillas.</span><span class="sxs-lookup"><span data-stu-id="932d7-139">There are tasks that will leverage connections into Azure to run the templates.</span></span> <span data-ttu-id="932d7-140">Los cambios en las plantillas de Administrador de recursos se aplican de forma incremental, lo que significa que para agregar un nuevo recurso, solo es necesario agregarlo a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="932d7-140">Changes to Resource Manager templates are applied incrementally, meaning that to add a new resource requires just adding it to the template.</span></span> <span data-ttu-id="932d7-141">Las herramientas de conciliarán las diferencias entre los recursos actuales y los definidos en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="932d7-141">The tooling will reconcile differences between the current resources and those defined in the template.</span></span> <span data-ttu-id="932d7-142">Los recursos se crearán o modificarán, de modo que coincidan con lo que se define en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="932d7-142">Resources will then be created or altered so they match what is defined in the template.</span></span>  

## <a name="terraform"></a><span data-ttu-id="932d7-143">Terraform</span><span class="sxs-lookup"><span data-stu-id="932d7-143">Terraform</span></span>

<span data-ttu-id="932d7-144">A menudo, las aplicaciones nativas de la nube están construidas para ser `cloud agnostic` .</span><span class="sxs-lookup"><span data-stu-id="932d7-144">Cloud-native applications are often constructed to be `cloud agnostic`.</span></span> <span data-ttu-id="932d7-145">Es decir, la aplicación no está estrechamente acoplada a un determinado proveedor de la nube y se puede implementar en cualquier nube pública.</span><span class="sxs-lookup"><span data-stu-id="932d7-145">Being so means the application isn't tightly coupled to a particular cloud vendor and can be deployed to any public cloud.</span></span>

<span data-ttu-id="932d7-146">[Terraform](https://www.terraform.io/) es una herramienta de plantillas comerciales que puede aprovisionar aplicaciones nativas en la nube en todos los principales reproductores en la nube: Azure, Google Cloud Platform, AWS y alicloud.</span><span class="sxs-lookup"><span data-stu-id="932d7-146">[Terraform](https://www.terraform.io/) is commercial templating tool that can provision cloud-native applications across all the major cloud players: Azure, Google Cloud Platform, AWS, and AliCloud.</span></span> <span data-ttu-id="932d7-147">En lugar de usar JSON como lenguaje de definición de plantillas, usa el YAML ligeramente más conciso.</span><span class="sxs-lookup"><span data-stu-id="932d7-147">Instead of using JSON as the template definition language, it uses the slightly more terse YAML.</span></span>

<span data-ttu-id="932d7-148">En la figura 10-16 se muestra un archivo terraform de ejemplo que hace lo mismo que la plantilla de Administrador de recursos anterior (Figura 10-15):</span><span class="sxs-lookup"><span data-stu-id="932d7-148">An example Terraform file that does the same as the previous Resource Manager template (Figure 10-15) is shown in Figure 10-16:</span></span>

```terraform
provider "azurerm" {
  version = "=1.28.0"
}

resource "azurerm_resource_group" "test" {
  name     = "production"
  location = "West US"
}

resource "azurerm_storage_account" "testsa" {
  name                     = "${var.storageAccountName}"
  resource_group_name      = "${azurerm_resource_group.testrg.name}"
  location                 = "${var.region}"
  account_tier             = "${var.tier}"
  account_replication_type = "${var.replicationType}"

}
```

<span data-ttu-id="932d7-149">**Figura 10-16** : ejemplo de una plantilla de administrador de recursos</span><span class="sxs-lookup"><span data-stu-id="932d7-149">**Figure 10-16** - An example of a Resource Manager template</span></span>

<span data-ttu-id="932d7-150">Terraform también proporciona mensajes de error intuitivos para las plantillas de problemas.</span><span class="sxs-lookup"><span data-stu-id="932d7-150">Terraform also provides intuitive error messages for problem templates.</span></span> <span data-ttu-id="932d7-151">También hay una tarea de validación útil que se puede usar en la fase de compilación para detectar los errores de plantilla con antelación.</span><span class="sxs-lookup"><span data-stu-id="932d7-151">There's also a handy validate task that can be used in the build phase to catch template errors early.</span></span>

<span data-ttu-id="932d7-152">Al igual que con las plantillas de Administrador de recursos, las herramientas de línea de comandos están disponibles para implementar plantillas terraform.</span><span class="sxs-lookup"><span data-stu-id="932d7-152">As with Resource Manager templates, command-line tools are available to deploy Terraform templates.</span></span> <span data-ttu-id="932d7-153">También hay tareas creadas por la comunidad en Azure Pipelines que pueden validar y aplicar plantillas terraform.</span><span class="sxs-lookup"><span data-stu-id="932d7-153">There are also community-created tasks in Azure Pipelines that can validate and apply Terraform templates.</span></span>

<span data-ttu-id="932d7-154">A veces, las plantillas terraform y ARM generan valores significativos, como una cadena de conexión a una base de datos recién creada.</span><span class="sxs-lookup"><span data-stu-id="932d7-154">Sometimes Terraform and ARM templates output meaningful values, such as a connection string to a newly created database.</span></span> <span data-ttu-id="932d7-155">Esta información se puede capturar en la canalización de compilación y usarse en tareas posteriores.</span><span class="sxs-lookup"><span data-stu-id="932d7-155">This information can be captured in the build pipeline and used in subsequent tasks.</span></span>

## <a name="azure-cli-scripts-and-tasks"></a><span data-ttu-id="932d7-156">CLI de Azure scripts y tareas</span><span class="sxs-lookup"><span data-stu-id="932d7-156">Azure CLI Scripts and Tasks</span></span>

<span data-ttu-id="932d7-157">Por último, puede aprovechar [CLI de Azure](https://docs.microsoft.com/cli/azure/) para crear un script de la infraestructura de la nube mediante declaración.</span><span class="sxs-lookup"><span data-stu-id="932d7-157">Finally, you can leverage [Azure CLI](https://docs.microsoft.com/cli/azure/) to declaratively script your cloud infrastructure.</span></span> <span data-ttu-id="932d7-158">CLI de Azure scripts se pueden crear, encontrar y compartir para aprovisionar y configurar prácticamente cualquier recurso de Azure.</span><span class="sxs-lookup"><span data-stu-id="932d7-158">Azure CLI scripts can be created, found, and shared to provision and configure almost any Azure resource.</span></span> <span data-ttu-id="932d7-159">La CLI es fácil de usar con una curva de aprendizaje suave.</span><span class="sxs-lookup"><span data-stu-id="932d7-159">The CLI is simple to use with a gentle learning curve.</span></span> <span data-ttu-id="932d7-160">Los scripts se ejecutan dentro de PowerShell o bash.</span><span class="sxs-lookup"><span data-stu-id="932d7-160">Scripts are executed within either PowerShell or Bash.</span></span> <span data-ttu-id="932d7-161">También son fáciles de depurar, especialmente cuando se comparan con las plantillas de ARM.</span><span class="sxs-lookup"><span data-stu-id="932d7-161">They're also straightforward to debug, especially when compared with ARM templates.</span></span>

<span data-ttu-id="932d7-162">CLI de Azure scripts funcionan bien cuando es necesario anular y volver a implementar la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="932d7-162">Azure CLI scripts work well when you need to tear down and redeploy your infrastructure.</span></span> <span data-ttu-id="932d7-163">Actualizar un entorno existente puede ser complicado.</span><span class="sxs-lookup"><span data-stu-id="932d7-163">Updating an existing environment can be tricky.</span></span> <span data-ttu-id="932d7-164">Muchos comandos de la CLI no son idempotente.</span><span class="sxs-lookup"><span data-stu-id="932d7-164">Many CLI commands aren't idempotent.</span></span> <span data-ttu-id="932d7-165">Esto significa que volverá a crear el recurso cada vez que se ejecuten, incluso si el recurso ya existe.</span><span class="sxs-lookup"><span data-stu-id="932d7-165">That means they'll recreate the resource each time they're run, even if the resource already exists.</span></span> <span data-ttu-id="932d7-166">Siempre es posible agregar código que Compruebe la existencia de cada recurso antes de crearlo.</span><span class="sxs-lookup"><span data-stu-id="932d7-166">It's always possible to add code that checks for the existence of each resource before creating it.</span></span> <span data-ttu-id="932d7-167">Pero, si lo hace, el script puede ser más difícil de administrar.</span><span class="sxs-lookup"><span data-stu-id="932d7-167">But, doing so, your script can become bloated and difficult to manage.</span></span>

<span data-ttu-id="932d7-168">Estos scripts también se pueden insertar en las canalizaciones de Azure DevOps como `Azure CLI tasks` .</span><span class="sxs-lookup"><span data-stu-id="932d7-168">These scripts can also be embedded in Azure DevOps pipelines as `Azure CLI tasks`.</span></span> <span data-ttu-id="932d7-169">La ejecución de la canalización invoca el script.</span><span class="sxs-lookup"><span data-stu-id="932d7-169">Executing the pipeline invokes the script.</span></span>

<span data-ttu-id="932d7-170">En la figura 10-17 se muestra un fragmento de código de YAML que muestra la versión de CLI de Azure y los detalles de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="932d7-170">Figure 10-17 shows a YAML snippet that lists the version of Azure CLI and the details of the subscription.</span></span> <span data-ttu-id="932d7-171">Observe cómo los comandos de CLI de Azure se incluyen en un script en línea.</span><span class="sxs-lookup"><span data-stu-id="932d7-171">Note how Azure CLI commands are included in an inline script.</span></span>

```yaml
- task: AzureCLI@2
  displayName: Azure CLI
  inputs:
    azureSubscription: <Name of the Azure Resource Manager service connection>
    scriptType: ps
    scriptLocation: inlineScript
    inlineScript: |
      az --version
      az account show
```

<span data-ttu-id="932d7-172">**Figura 10-17** -script de CLI de Azure</span><span class="sxs-lookup"><span data-stu-id="932d7-172">**Figure 10-17** - Azure CLI script</span></span>

<span data-ttu-id="932d7-173">En el artículo [¿Qué es la infraestructura como código](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)? Author Sam Guckenheimer describe cómo "los equipos que implementan IaC pueden ofrecer entornos estables rápidamente y a escala.</span><span class="sxs-lookup"><span data-stu-id="932d7-173">In the article, [What is Infrastructure as Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), Author Sam Guckenheimer describes how, "Teams who implement IaC can deliver stable environments rapidly and at scale.</span></span> <span data-ttu-id="932d7-174">Los equipos evitan la configuración manual de los entornos y aplican la coherencia al representar el estado deseado de sus entornos a través del código.</span><span class="sxs-lookup"><span data-stu-id="932d7-174">Teams avoid manual configuration of environments and enforce consistency by representing the desired state of their environments via code.</span></span> <span data-ttu-id="932d7-175">Las implementaciones de infraestructura con IaC se pueden repetir y evitan problemas en tiempo de ejecución causados por el desfase de la configuración o las dependencias que faltan.</span><span class="sxs-lookup"><span data-stu-id="932d7-175">Infrastructure deployments with IaC are repeatable and prevent runtime issues caused by configuration drift or missing dependencies.</span></span> <span data-ttu-id="932d7-176">Los equipos de DevOps pueden trabajar junto con un conjunto unificado de prácticas y herramientas para ofrecer aplicaciones y su infraestructura de soporte de forma rápida, confiable y a escala ".</span><span class="sxs-lookup"><span data-stu-id="932d7-176">DevOps teams can work together with a unified set of practices and tools to deliver applications and their supporting infrastructure rapidly, reliably, and at scale."</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="932d7-177">[Anterior](feature-flags.md)
>[Siguiente](application-bundles.md)</span><span class="sxs-lookup"><span data-stu-id="932d7-177">[Previous](feature-flags.md)
[Next](application-bundles.md)</span></span>
