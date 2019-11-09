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
# <a name="infrastructure-as-code"></a>Infraestructura como código

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Las aplicaciones nativas de la nube tienden a hacer uso de todo tipo de componentes de plataforma como servicio (PaaS) fantásticos. En una plataforma en la nube como Azure, estos componentes pueden incluir elementos como Storage, Service Bus y Signalr Service. A medida que las aplicaciones son más complicadas, es probable que el número de estos servicios en uso crezca. Del mismo modo que la entrega continua rompió el modelo tradicional de implementación en un entorno de forma manual, el rápido ritmo de cambio también dañó el modelo de tener un grupo de ti centralizado para administrar entornos.

También se pueden automatizar los entornos de compilación. Hay una amplia gama de herramientas muy compensadas que pueden facilitar el proceso.

## <a name="azure-resource-manager-templates"></a>Plantillas de Azure Resource Manager

Azure Resource Manager plantillas son un lenguaje basado en JSON para definir varios recursos en Azure. El esquema básico tiene un aspecto similar al de la figura 11-10.

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

**Figura 11-10** : el esquema de una plantilla de administrador de recursos

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

**Figura 11-11** : ejemplo de una cuenta de almacenamiento definida en una plantilla de administrador de recursos

Las plantillas se pueden parametrizar para que se pueda reutilizar una plantilla con distintas configuraciones para definir entornos de desarrollo, QA y producción. Esto ayuda a eliminar sorpresas al migrar a un entorno superior que está configurado de forma diferente en los entornos inferiores. Normalmente, los recursos definidos en una plantilla se crean dentro de un único grupo de recursos en Azure (es posible definir varios grupos de recursos en una sola plantilla de Administrador de recursos pero inusual). Esto facilita la eliminación de un entorno con solo eliminar el grupo de recursos en su totalidad. El análisis de costos también se puede ejecutar en el nivel de grupo de recursos, lo que permite una rápida contabilización de la cantidad de costos de cada entorno.

Hay muchas plantillas de ejemplo definidas en el proyecto de [plantillas de inicio rápido de Azure](https://github.com/Azure/azure-quickstart-templates) en github que dará una partida al iniciarse en una plantilla nueva o al agregarse a una existente.

Administrador de recursos plantillas se pueden ejecutar de varias maneras. Quizás la manera más sencilla consiste en pegarlos simplemente en el Azure Portal. En el caso de las implementaciones experimentales, este método puede ser muy rápido. También se pueden ejecutar como parte de un proceso de compilación o lanzamiento en Azure DevOps. Hay tareas que aprovecharán las conexiones en Azure para ejecutar las plantillas. Los cambios en las plantillas de Administrador de recursos se aplican de forma incremental, lo que significa que para agregar un nuevo recurso, solo es necesario agregarlo a la plantilla. Las herramientas controlarán la diferenciación del grupo de recursos actual con el grupo de recursos deseado definido en la plantilla. Los recursos se crearán o modificarán, de modo que coincidan con lo que se define en la plantilla.  

## <a name="terraform"></a>Terraform

Un inconveniente percibido de las plantillas de Administrador de recursos es que son específicas de la nube de Azure. No es habitual crear aplicaciones que incluyen recursos de más de una nube, pero en los casos en los que el negocio se basa en un tiempo de actividad increíble, el costo de admitir varias nubes podría merecer la pena. Si había un lenguaje de plantillas que podría usarse en todas las nubes, también podría permitir que los conocimientos para desarrolladores fueran mucho más portátiles.

Existen varias tecnologías que hacen eso. La oferta más madura en ese espacio se conoce como [terraform](https://www.terraform.io/). Terraform es compatible con todos los principales reproductores en la nube, como Azure, Google Cloud Platform, AWS y alicloud, y también admite docenas de reproductores menores como Heroku y DigitalOcean. En lugar de usar JSON como lenguaje de definición de plantillas, usa el YAML ligeramente más conciso.

En la figura 11-12 se muestra un archivo terraform de ejemplo que hace lo mismo que la plantilla de Administrador de recursos anterior (Figura 11-11):

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

**Figura 11-12** : ejemplo de una plantilla de administrador de recursos

Terraform realiza un mejor trabajo de proporcionar mensajes de error razonables cuando no se puede implementar un recurso debido a un error en la plantilla. Se trata de un área en la que Administrador de recursos plantillas tienen algunos desafíos continuos. También hay una tarea de validación muy útil que se puede usar en la fase de compilación para detectar los errores de plantilla con antelación.

Al igual que con las plantillas de Administrador de recursos, existen herramientas de línea de comandos que se pueden usar para implementar plantillas terraform. También hay tareas creadas por la comunidad en Azure Pipelines que pueden validar y aplicar plantillas terraform.

En caso de que la plantilla terraform o Administrador de recursos genere valores interesantes, como la cadena de conexión a una base de datos recién creada, se pueden capturar en la canalización de compilación y usarse en tareas posteriores.

>[!div class="step-by-step"]
>[Anterior](devops.md)
>[Siguiente](application-bundles.md)
