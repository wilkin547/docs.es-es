---
title: Infraestructura como código
description: Adopción de infraestructura como código (IaC) con aplicaciones nativas de la nube
ms.date: 05/13/2020
ms.openlocfilehash: cfc9e1f0b2733048d5921de5a0400998c282b1fa
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613959"
---
# <a name="infrastructure-as-code"></a>Infraestructura como código

Los sistemas nativos en la nube adoptan microservicios, contenedores y un diseño moderno del sistema para lograr la velocidad y la agilidad. Proporcionan fases automatizadas de compilación y versión para garantizar un código coherente y de calidad. Pero eso es solo parte de la historia. ¿Cómo se aprovisionan los entornos de nube en los que se ejecutan estos sistemas?

Las modernas aplicaciones nativas en la nube adoptan la práctica ampliamente aceptada de [infraestructura como código](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), o `IaC` .  Con IaC, puede automatizar el aprovisionamiento de plataforma. Esencialmente, aplica prácticas de ingeniería de software, como pruebas y control de versiones a las prácticas de DevOps. La infraestructura y las implementaciones son automatizadas, coherentes y repetibles. Del mismo modo que la entrega continua automatiza el modelo tradicional de implementaciones manuales, la infraestructura como código (IaC) está evolucionando el modo en que se administran los entornos de aplicación.

Herramientas como Azure Resource Manager (ARM), terraform y la interfaz de la línea de comandos (CLI) de Azure le permiten crear un script de la infraestructura de la nube que necesita mediante declaración.

## <a name="azure-resource-manager-templates"></a>Plantillas del Administrador de recursos de Azure

ARM significa [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/). Es un motor de aprovisionamiento de API que se integra en Azure y se expone como un servicio de API. ARM permite implementar, actualizar, eliminar y administrar los recursos contenidos en el grupo de recursos de Azure en una única operación coordinada. El motor se proporciona con una plantilla basada en JSON que especifica los recursos necesarios y su configuración. ARM organiza automáticamente la implementación en el orden correcto que respeta las dependencias. El motor de garantiza Idempotencia. Si ya existe un recurso deseado con la misma configuración, se omitirá el aprovisionamiento.

Azure Resource Manager plantillas son un lenguaje basado en JSON para definir varios recursos en Azure. El esquema básico tiene un aspecto similar al de la figura 10-14.

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

**Figura 10-14** : el esquema de una plantilla de administrador de recursos

Dentro de esta plantilla, se puede definir un contenedor de almacenamiento dentro de la sección de recursos, como por ejemplo:

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

**Figura 10-15** : ejemplo de una cuenta de almacenamiento definida en una plantilla de administrador de recursos

Una plantilla de ARM se puede parametrizar con información de entorno y configuración dinámica. De este modo, se puede reutilizar para definir diferentes entornos, como desarrollo, QA o producción. Normalmente, la plantilla crea todos los recursos de un único grupo de recursos de Azure. Es posible definir varios grupos de recursos en una sola plantilla de Administrador de recursos, si es necesario. Puede eliminar todos los recursos de un entorno eliminando el propio grupo de recursos. El análisis de costos también se puede ejecutar en el nivel de grupo de recursos, lo que permite una rápida contabilización de la cantidad de costos de cada entorno.

Hay muchos ejemplos o plantillas de ARM disponibles en el proyecto de [plantillas de inicio rápido de Azure](https://github.com/Azure/azure-quickstart-templates) en github. Pueden ayudar a acelerar la creación de una nueva plantilla o la modificación de una existente.

Administrador de recursos plantillas se pueden ejecutar de muchas maneras. Quizás la manera más sencilla consiste en pegarlos simplemente en el Azure Portal. En el caso de las implementaciones experimentales, este método puede ser rápido. También se pueden ejecutar como parte de un proceso de compilación o lanzamiento en Azure DevOps. Hay tareas que aprovecharán las conexiones en Azure para ejecutar las plantillas. Los cambios en las plantillas de Administrador de recursos se aplican de forma incremental, lo que significa que para agregar un nuevo recurso, solo es necesario agregarlo a la plantilla. Las herramientas de conciliarán las diferencias entre los recursos actuales y los definidos en la plantilla. Los recursos se crearán o modificarán, de modo que coincidan con lo que se define en la plantilla.  

## <a name="terraform"></a>Terraform

A menudo, las aplicaciones nativas de la nube están construidas para ser `cloud agnostic` . Es decir, la aplicación no está estrechamente acoplada a un determinado proveedor de la nube y se puede implementar en cualquier nube pública.

[Terraform](https://www.terraform.io/) es una herramienta de plantillas comerciales que puede aprovisionar aplicaciones nativas en la nube en todos los principales reproductores en la nube: Azure, Google Cloud Platform, AWS y alicloud. En lugar de usar JSON como lenguaje de definición de plantillas, usa el YAML ligeramente más conciso.

En la figura 10-16 se muestra un archivo terraform de ejemplo que hace lo mismo que la plantilla de Administrador de recursos anterior (Figura 10-15):

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

**Figura 10-16** : ejemplo de una plantilla de administrador de recursos

Terraform también proporciona mensajes de error intuitivos para las plantillas de problemas. También hay una tarea de validación útil que se puede usar en la fase de compilación para detectar los errores de plantilla con antelación.

Al igual que con las plantillas de Administrador de recursos, las herramientas de línea de comandos están disponibles para implementar plantillas terraform. También hay tareas creadas por la comunidad en Azure Pipelines que pueden validar y aplicar plantillas terraform.

A veces, las plantillas terraform y ARM generan valores significativos, como una cadena de conexión a una base de datos recién creada. Esta información se puede capturar en la canalización de compilación y usarse en tareas posteriores.

## <a name="azure-cli-scripts-and-tasks"></a>CLI de Azure scripts y tareas

Por último, puede aprovechar [CLI de Azure](https://docs.microsoft.com/cli/azure/) para crear un script de la infraestructura de la nube mediante declaración. CLI de Azure scripts se pueden crear, encontrar y compartir para aprovisionar y configurar prácticamente cualquier recurso de Azure. La CLI es fácil de usar con una curva de aprendizaje suave. Los scripts se ejecutan dentro de PowerShell o bash. También son fáciles de depurar, especialmente cuando se comparan con las plantillas de ARM.

CLI de Azure scripts funcionan bien cuando es necesario anular y volver a implementar la infraestructura. Actualizar un entorno existente puede ser complicado. Muchos comandos de la CLI no son idempotente. Esto significa que volverá a crear el recurso cada vez que se ejecuten, incluso si el recurso ya existe. Siempre es posible agregar código que Compruebe la existencia de cada recurso antes de crearlo. Pero, si lo hace, el script puede ser más difícil de administrar.

Estos scripts también se pueden insertar en las canalizaciones de Azure DevOps como `Azure CLI tasks` . La ejecución de la canalización invoca el script.

En la figura 10-17 se muestra un fragmento de código de YAML que muestra la versión de CLI de Azure y los detalles de la suscripción. Observe cómo los comandos de CLI de Azure se incluyen en un script en línea.

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

**Figura 10-17** -script de CLI de Azure

En el artículo [¿Qué es la infraestructura como código](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)? Author Sam Guckenheimer describe cómo "los equipos que implementan IaC pueden ofrecer entornos estables rápidamente y a escala. Los equipos evitan la configuración manual de los entornos y aplican la coherencia al representar el estado deseado de sus entornos a través del código. Las implementaciones de infraestructura con IaC se pueden repetir y evitan problemas en tiempo de ejecución causados por el desfase de la configuración o las dependencias que faltan. Los equipos de DevOps pueden trabajar junto con un conjunto unificado de prácticas y herramientas para ofrecer aplicaciones y su infraestructura de soporte de forma rápida, confiable y a escala ".

>[!div class="step-by-step"]
>[Anterior](feature-flags.md)
>[Siguiente](application-bundles.md)
