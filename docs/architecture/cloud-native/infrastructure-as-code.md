---
title: Infraestructura como código
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Infraestructura como código
ms.date: 06/30/2019
ms.openlocfilehash: 3957da68ac28774f899f49fb181a29c2435902f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841784"
---
# <a name="infrastructure-as-code"></a><span data-ttu-id="c78f2-103">Infraestructura como código</span><span class="sxs-lookup"><span data-stu-id="c78f2-103">Infrastructure as code</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="c78f2-104">Las aplicaciones nativas de la nube tienden a hacer uso de todo tipo de componentes de plataforma como servicio (PaaS) fantásticos.</span><span class="sxs-lookup"><span data-stu-id="c78f2-104">Cloud-native applications tend to make use of all sorts of fantastic platform as a service (PaaS) components.</span></span> <span data-ttu-id="c78f2-105">En una plataforma en la nube como Azure, estos componentes pueden incluir elementos como Storage, Service Bus y Signalr Service.</span><span class="sxs-lookup"><span data-stu-id="c78f2-105">On a cloud platform like Azure, these components might include things like storage, Service Bus, and the SignalR service.</span></span> <span data-ttu-id="c78f2-106">A medida que las aplicaciones son más complicadas, es probable que el número de estos servicios en uso crezca.</span><span class="sxs-lookup"><span data-stu-id="c78f2-106">As applications become more complicated, the number of these services in use is likely to grow.</span></span> <span data-ttu-id="c78f2-107">Del mismo modo que la entrega continua rompió el modelo tradicional de implementación en un entorno de forma manual, el rápido ritmo de cambio también dañó el modelo de tener un grupo de ti centralizado para administrar entornos.</span><span class="sxs-lookup"><span data-stu-id="c78f2-107">Just as how continuous delivery broke the traditional model of deploying to an environment manually, the rapid pace of change also broke the model of having a centralized IT group manage environments.</span></span>

<span data-ttu-id="c78f2-108">También se pueden automatizar los entornos de compilación.</span><span class="sxs-lookup"><span data-stu-id="c78f2-108">Building environments can, and should, also be automated.</span></span> <span data-ttu-id="c78f2-109">Hay una amplia gama de herramientas muy compensadas que pueden facilitar el proceso.</span><span class="sxs-lookup"><span data-stu-id="c78f2-109">There's a wide range of well thought out tools that can make the process easy.</span></span>

## <a name="azure-resource-manager-templates"></a><span data-ttu-id="c78f2-110">Plantillas de Azure Resource Manager</span><span class="sxs-lookup"><span data-stu-id="c78f2-110">Azure Resource Manager templates</span></span>

<span data-ttu-id="c78f2-111">Azure Resource Manager plantillas son un lenguaje basado en JSON para definir varios recursos en Azure.</span><span class="sxs-lookup"><span data-stu-id="c78f2-111">Azure Resource Manager templates are a JSON-based language for defining various resources in Azure.</span></span> <span data-ttu-id="c78f2-112">El esquema básico tiene un aspecto similar al de la figura 11-10.</span><span class="sxs-lookup"><span data-stu-id="c78f2-112">The basic schema looks something like Figure 11-10.</span></span>

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

<span data-ttu-id="c78f2-113">**Figura 11-10** : el esquema de una plantilla de administrador de recursos</span><span class="sxs-lookup"><span data-stu-id="c78f2-113">**Figure 11-10** - The schema for a Resource Manager template</span></span>

<span data-ttu-id="c78f2-114">Dentro de esta plantilla, se puede definir un contenedor de almacenamiento dentro de la sección de recursos, como por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c78f2-114">Within this template, one might define a storage container inside the resources section like so:</span></span>

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

<span data-ttu-id="c78f2-115">**Figura 11-11** : ejemplo de una cuenta de almacenamiento definida en una plantilla de administrador de recursos</span><span class="sxs-lookup"><span data-stu-id="c78f2-115">**Figure 11-11** - An example of a storage account defined in a Resource Manager template</span></span>

<span data-ttu-id="c78f2-116">Las plantillas se pueden parametrizar para que se pueda reutilizar una plantilla con distintas configuraciones para definir entornos de desarrollo, QA y producción.</span><span class="sxs-lookup"><span data-stu-id="c78f2-116">The templates can be parameterized so that one template can be reused with different settings to define development, QA, and production environments.</span></span> <span data-ttu-id="c78f2-117">Esto ayuda a eliminar sorpresas al migrar a un entorno superior que está configurado de forma diferente en los entornos inferiores.</span><span class="sxs-lookup"><span data-stu-id="c78f2-117">This helps eliminate surprises when migrating to a higher environment that is set up differently from the lower environments.</span></span> <span data-ttu-id="c78f2-118">Normalmente, los recursos definidos en una plantilla se crean dentro de un único grupo de recursos en Azure (es posible definir varios grupos de recursos en una sola plantilla de Administrador de recursos pero inusual).</span><span class="sxs-lookup"><span data-stu-id="c78f2-118">The resources defined in a template are typically all created within a single resource group on Azure (it's possible to define multiple resource groups in a single Resource Manager template but unusual).</span></span> <span data-ttu-id="c78f2-119">Esto facilita la eliminación de un entorno con solo eliminar el grupo de recursos en su totalidad.</span><span class="sxs-lookup"><span data-stu-id="c78f2-119">This makes it very easy to delete an environment by just deleting the resource group as a whole.</span></span> <span data-ttu-id="c78f2-120">El análisis de costos también se puede ejecutar en el nivel de grupo de recursos, lo que permite una rápida contabilización de la cantidad de costos de cada entorno.</span><span class="sxs-lookup"><span data-stu-id="c78f2-120">Cost analysis can also be run at the resource group level, allowing for quick accounting of how much each environment is costing.</span></span>

<span data-ttu-id="c78f2-121">Hay muchas plantillas de ejemplo definidas en el proyecto de [plantillas de inicio rápido de Azure](https://github.com/Azure/azure-quickstart-templates) en github que dará una partida al iniciarse en una plantilla nueva o al agregarse a una existente.</span><span class="sxs-lookup"><span data-stu-id="c78f2-121">There are many example templates defined in the [Azure Quickstart Templates](https://github.com/Azure/azure-quickstart-templates) project on GitHub that will give a leg up when starting on a new template or adding to an existing one.</span></span>

<span data-ttu-id="c78f2-122">Administrador de recursos plantillas se pueden ejecutar de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="c78f2-122">Resource Manager templates can be run in a variety of ways.</span></span> <span data-ttu-id="c78f2-123">Quizás la manera más sencilla consiste en pegarlos simplemente en el Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="c78f2-123">Perhaps the simplest way is to simply paste them into the Azure portal.</span></span> <span data-ttu-id="c78f2-124">En el caso de las implementaciones experimentales, este método puede ser muy rápido.</span><span class="sxs-lookup"><span data-stu-id="c78f2-124">For experimental deployments, this method can be very quick.</span></span> <span data-ttu-id="c78f2-125">También se pueden ejecutar como parte de un proceso de compilación o lanzamiento en Azure DevOps.</span><span class="sxs-lookup"><span data-stu-id="c78f2-125">They can also be run as part of a build or release process in Azure DevOps.</span></span> <span data-ttu-id="c78f2-126">Hay tareas que aprovecharán las conexiones en Azure para ejecutar las plantillas.</span><span class="sxs-lookup"><span data-stu-id="c78f2-126">There are tasks that will leverage connections into Azure to run the templates.</span></span> <span data-ttu-id="c78f2-127">Los cambios en las plantillas de Administrador de recursos se aplican de forma incremental, lo que significa que para agregar un nuevo recurso, solo es necesario agregarlo a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c78f2-127">Changes to Resource Manager templates are applied incrementally, meaning that to add a new resource requires just adding it to the template.</span></span> <span data-ttu-id="c78f2-128">Las herramientas controlarán la diferenciación del grupo de recursos actual con el grupo de recursos deseado definido en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c78f2-128">The tooling will handle diffing the current resource group with the desired resource group defined in the template.</span></span> <span data-ttu-id="c78f2-129">Los recursos se crearán o modificarán, de modo que coincidan con lo que se define en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c78f2-129">Resources will then be created or altered so they match what is defined in the template.</span></span>  

## <a name="terraform"></a><span data-ttu-id="c78f2-130">Terraform</span><span class="sxs-lookup"><span data-stu-id="c78f2-130">Terraform</span></span>

<span data-ttu-id="c78f2-131">Un inconveniente percibido de las plantillas de Administrador de recursos es que son específicas de la nube de Azure.</span><span class="sxs-lookup"><span data-stu-id="c78f2-131">A perceived disadvantage of Resource Manager templates is that they are specific to the Azure cloud.</span></span> <span data-ttu-id="c78f2-132">No es habitual crear aplicaciones que incluyen recursos de más de una nube, pero en los casos en los que el negocio se basa en un tiempo de actividad increíble, el costo de admitir varias nubes podría merecer la pena.</span><span class="sxs-lookup"><span data-stu-id="c78f2-132">It's unusual to create applications that include resources from more than one cloud, but in cases where the business relies on spectacular uptime, the cost of supporting multiple clouds might be worthwhile.</span></span> <span data-ttu-id="c78f2-133">Si había un lenguaje de plantillas que podría usarse en todas las nubes, también podría permitir que los conocimientos para desarrolladores fueran mucho más portátiles.</span><span class="sxs-lookup"><span data-stu-id="c78f2-133">If there were one templating language that could be used across every cloud, then it would also allow for developer skills to be much more portable.</span></span>

<span data-ttu-id="c78f2-134">Existen varias tecnologías que hacen eso.</span><span class="sxs-lookup"><span data-stu-id="c78f2-134">Several technologies exist which do just that!</span></span> <span data-ttu-id="c78f2-135">La oferta más madura en ese espacio se conoce como [terraform](https://www.terraform.io/).</span><span class="sxs-lookup"><span data-stu-id="c78f2-135">The most mature offering in that space is known as [Terraform](https://www.terraform.io/).</span></span> <span data-ttu-id="c78f2-136">Terraform es compatible con todos los principales reproductores en la nube, como Azure, Google Cloud Platform, AWS y alicloud, y también admite docenas de reproductores menores como Heroku y DigitalOcean.</span><span class="sxs-lookup"><span data-stu-id="c78f2-136">Terraform supports every major cloud player such as Azure, Google Cloud Platform, AWS, and AliCloud, and it also supports dozens of minor players such as Heroku and DigitalOcean.</span></span> <span data-ttu-id="c78f2-137">En lugar de usar JSON como lenguaje de definición de plantillas, usa el YAML ligeramente más conciso.</span><span class="sxs-lookup"><span data-stu-id="c78f2-137">Instead of using JSON as the template definition language, it uses the slightly more terse YAML.</span></span>

<span data-ttu-id="c78f2-138">En la figura 11-12 se muestra un archivo terraform de ejemplo que hace lo mismo que la plantilla de Administrador de recursos anterior (Figura 11-11):</span><span class="sxs-lookup"><span data-stu-id="c78f2-138">An example Terraform file that does the same as the previous Resource Manager template (Figure 11-11) is shown in Figure 11-12:</span></span>

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

<span data-ttu-id="c78f2-139">**Figura 11-12** : ejemplo de una plantilla de administrador de recursos</span><span class="sxs-lookup"><span data-stu-id="c78f2-139">**Figure 11-12** - An example of a Resource Manager template</span></span>

<span data-ttu-id="c78f2-140">Terraform realiza un mejor trabajo de proporcionar mensajes de error razonables cuando no se puede implementar un recurso debido a un error en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c78f2-140">Terraform does a better job of providing sensible error messages when a resource can't be deployed because of an error in the template.</span></span> <span data-ttu-id="c78f2-141">Se trata de un área en la que Administrador de recursos plantillas tienen algunos desafíos continuos.</span><span class="sxs-lookup"><span data-stu-id="c78f2-141">This is an area where Resource Manager templates have some ongoing challenges.</span></span> <span data-ttu-id="c78f2-142">También hay una tarea de validación muy útil que se puede usar en la fase de compilación para detectar los errores de plantilla con antelación.</span><span class="sxs-lookup"><span data-stu-id="c78f2-142">There's also a very handy validate task that can be used in the build phase to catch template errors early.</span></span>

<span data-ttu-id="c78f2-143">Al igual que con las plantillas de Administrador de recursos, existen herramientas de línea de comandos que se pueden usar para implementar plantillas terraform.</span><span class="sxs-lookup"><span data-stu-id="c78f2-143">As with Resource Manager templates, there are command-line tools that can be used to deploy Terraform templates.</span></span> <span data-ttu-id="c78f2-144">También hay tareas creadas por la comunidad en Azure Pipelines que pueden validar y aplicar plantillas terraform.</span><span class="sxs-lookup"><span data-stu-id="c78f2-144">There are also community-created tasks in Azure Pipelines that can validate and apply Terraform templates.</span></span>

<span data-ttu-id="c78f2-145">En caso de que la plantilla terraform o Administrador de recursos genere valores interesantes, como la cadena de conexión a una base de datos recién creada, se pueden capturar en la canalización de compilación y usarse en tareas posteriores.</span><span class="sxs-lookup"><span data-stu-id="c78f2-145">In the event that the Terraform or Resource Manager template outputs interesting values such as the connection string to a newly created database they can be captured in the build pipeline and used in subsequent tasks.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c78f2-146">[Anterior](devops.md)
>[Siguiente](application-bundles.md)</span><span class="sxs-lookup"><span data-stu-id="c78f2-146">[Previous](devops.md)
[Next](application-bundles.md)</span></span>
