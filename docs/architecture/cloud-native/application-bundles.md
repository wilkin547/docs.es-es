---
title: Agrupaciones de aplicaciones nativas en la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Agrupaciones de aplicaciones nativas en la nube
ms.date: 06/30/2019
ms.openlocfilehash: 6f85ca14ff4d17f9c7a90a9ace51a1448b89fcb3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895682"
---
# <a name="cloud-native-application-bundles"></a>Agrupaciones de aplicaciones nativas en la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Una propiedad clave de las aplicaciones nativas en la nube es que aprovechan las propiedades de la nube para acelerar el desarrollo. Esto suele significar que una aplicación completa utiliza diferentes tipos de tecnologías. Las aplicaciones pueden enviarse en contenedores de Docker, algunos servicios pueden usar Azure Functions mientras que otras pueden ejecutarse directamente en máquinas virtuales asignadas en servidores de gran tamaño con la aceleración de GPU de hardware. Dos aplicaciones nativas en la nube no son las mismas, por lo que resulta difícil proporcionar un único mecanismo para enviarlas.

Los contenedores de Docker se pueden ejecutar en Kubernetes mediante un gráfico de Helm para la implementación. El Azure Functions se puede asignar mediante plantillas terraform. Por último, las máquinas virtuales se pueden asignar mediante terraform pero se crean con ansible. Se trata de una gran cantidad de tecnologías y no ha sido posible empaquetarlas todas juntas en un paquete razonable. Hasta ahora.

Los paquetes de aplicaciones nativas en la nube (CNABs) son un esfuerzo conjunto de varias empresas de la comunidad, como Microsoft, Docker y HashiCorp, para desarrollar una especificación para empaquetar aplicaciones distribuidas.

El esfuerzo se anunció en diciembre de 2018, por lo que sigue habiendo un poco de trabajo para exponer el esfuerzo a la mayor comunidad. Sin embargo, ya existe una [especificación Open](https://github.com/deislabs/cnab-spec) y una implementación de referencia conocida como [duffle](https://duffle.sh/). Esta herramienta, que se escribió en Go, es un esfuerzo conjunto entre Docker y Microsoft.

CNABs puede contener diferentes tipos de tecnologías de instalación. Esto permite que elementos como gráficos de Helm, plantillas de terraform y guías de ansible coexistan en el mismo paquete. Una vez creados, los paquetes son independientes y portátiles; se pueden instalar desde un stick USB.  Los paquetes se firman criptográficamente para asegurarse de que se originan en la entidad que notifican.

El núcleo de un CNAB es un archivo denominado `bundle.json`. Este archivo define el contenido de la agrupación, se terraform o imágenes o cualquier otro elemento. En la figura 11-9 se define un CNAB que invoca algunos terraform. No obstante, tenga en cuenta que en realidad se define una imagen de invocación que se usa para invocar terraform. Cuando se empaqueta, el archivo de Docker que se encuentra en el directorio *CNAB* se integra en una imagen de Docker, que se incluirá en la agrupación. Tener terraform instalado dentro de un contenedor de Docker en el paquete significa que los usuarios no necesitan tener terraform instalado en su equipo para ejecutar la agrupación.

```json
{
    "name": "terraform",
    "version": "0.1.0",
    "schemaVersion": "v1.0.0-WD",
    "parameters": {
        "backend": {
            "type": "boolean",
            "defaultValue": false,
            "destination": {
                "env": "TF_VAR_backend"
            }
        }
    },
    "invocationImages": [
        {
        "imageType": "docker",
        "image": "cnab/terraform:latest"
        }
    ],
    "credentials": {
        "tenant_id": {
            "env": "TF_VAR_tenant_id"
        },
        "client_id": {
            "env": "TF_VAR_client_id"
        },
        "client_secret": {
            "env": "TF_VAR_client_secret"
        },
        "subscription_id": {
            "env": "TF_VAR_subscription_id"
        },
        "ssh_authorized_key": {
            "env": "TF_VAR_ssh_authorized_key"
        }
    },
    "actions": {
        "status": {
            "modifies": true
        }
    }
}
```

**Figura 11-13** : un archivo de terraform de ejemplo

`bundle.json` También define un conjunto de parámetros que se pasan en terraform. La parametrización de la agrupación permite la instalación en diversos entornos diferentes.

El formato CNAB también es flexible, lo que permite su uso en cualquier nube. Incluso se puede usar en soluciones locales como [OpenStack](https://www.openstack.org/).

## <a name="devops-decisions"></a>Decisiones de DevOps

Hay tantas herramientas excelentes en el espacio de DevOps estos días, así como libros y documentos más fantásticos sobre cómo hacerlo correctamente. Un libro favorito para empezar en el recorrido de DevOps es [el proyecto Phoenix](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), que sigue la transformación de una empresa ficticia de NOOP a DevOps. Lo único que hay que hacer es que DevOps ya no sea un "bonito" cuando se implementen aplicaciones nativas complejas en la nube. Es un requisito y debe planearse y reescribirse al principio de cualquier proyecto.

>[!div class="step-by-step"]
>[Anterior](infrastructure-as-code.md)
>[Siguiente](summary.md)
