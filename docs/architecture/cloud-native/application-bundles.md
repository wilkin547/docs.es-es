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
# <a name="cloud-native-application-bundles"></a><span data-ttu-id="ed8d2-103">Agrupaciones de aplicaciones nativas en la nube</span><span class="sxs-lookup"><span data-stu-id="ed8d2-103">Cloud Native Application Bundles</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="ed8d2-104">Una propiedad clave de las aplicaciones nativas en la nube es que aprovechan las propiedades de la nube para acelerar el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-104">A key property of cloud-native applications is that they leverage the properties of the cloud to speed up development.</span></span> <span data-ttu-id="ed8d2-105">Esto suele significar que una aplicación completa utiliza diferentes tipos de tecnologías.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-105">This often means that a full application uses different kinds of technologies.</span></span> <span data-ttu-id="ed8d2-106">Las aplicaciones pueden enviarse en contenedores de Docker, algunos servicios pueden usar Azure Functions mientras que otras pueden ejecutarse directamente en máquinas virtuales asignadas en servidores de gran tamaño con la aceleración de GPU de hardware.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-106">Applications may be shipped in Docker containers, some services may use Azure Functions while other parts may run directly on virtual machines allocated on large metal servers with hardware GPU acceleration.</span></span> <span data-ttu-id="ed8d2-107">Dos aplicaciones nativas en la nube no son las mismas, por lo que resulta difícil proporcionar un único mecanismo para enviarlas.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-107">No two cloud-native applications are the same, so it's been difficult to provide a single mechanism for shipping them.</span></span>

<span data-ttu-id="ed8d2-108">Los contenedores de Docker se pueden ejecutar en Kubernetes mediante un gráfico de Helm para la implementación.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-108">The Docker containers may run on Kubernetes using a Helm Chart for deployment.</span></span> <span data-ttu-id="ed8d2-109">El Azure Functions se puede asignar mediante plantillas terraform.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-109">The Azure Functions may be allocated using Terraform templates.</span></span> <span data-ttu-id="ed8d2-110">Por último, las máquinas virtuales se pueden asignar mediante terraform pero se crean con ansible.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-110">Finally, the virtual machines may be allocated using Terraform but built out using Ansible.</span></span> <span data-ttu-id="ed8d2-111">Se trata de una gran cantidad de tecnologías y no ha sido posible empaquetarlas todas juntas en un paquete razonable.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-111">This is a whole mess of technologies and there has been no way to package them all together into a reasonable package.</span></span> <span data-ttu-id="ed8d2-112">Hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-112">Until now.</span></span>

<span data-ttu-id="ed8d2-113">Los paquetes de aplicaciones nativas en la nube (CNABs) son un esfuerzo conjunto de varias empresas de la comunidad, como Microsoft, Docker y HashiCorp, para desarrollar una especificación para empaquetar aplicaciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-113">Cloud Native Application Bundles (CNABs) are a joint effort of a number of community-minded companies such as Microsoft, Docker, and HashiCorp to develop a specification to package distributed applications.</span></span>

<span data-ttu-id="ed8d2-114">El esfuerzo se anunció en diciembre de 2018, por lo que sigue habiendo un poco de trabajo para exponer el esfuerzo a la mayor comunidad.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-114">The effort was announced in December of 2018, so there's still a fair bit of work to do to expose the effort to the greater community.</span></span> <span data-ttu-id="ed8d2-115">Sin embargo, ya existe una [especificación Open](https://github.com/deislabs/cnab-spec) y una implementación de referencia conocida como [duffle](https://duffle.sh/).</span><span class="sxs-lookup"><span data-stu-id="ed8d2-115">However, there's already an [open specification](https://github.com/deislabs/cnab-spec) and a reference implementation known as [Duffle](https://duffle.sh/).</span></span> <span data-ttu-id="ed8d2-116">Esta herramienta, que se escribió en Go, es un esfuerzo conjunto entre Docker y Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-116">This tool, which was written in Go, is a joint effort between Docker and Microsoft.</span></span>

<span data-ttu-id="ed8d2-117">CNABs puede contener diferentes tipos de tecnologías de instalación.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-117">The CNABs can contain different kinds of installation technologies.</span></span> <span data-ttu-id="ed8d2-118">Esto permite que elementos como gráficos de Helm, plantillas de terraform y guías de ansible coexistan en el mismo paquete.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-118">This allows things like Helm Charts, Terraform templates, and Ansible Playbooks to coexist in the same package.</span></span> <span data-ttu-id="ed8d2-119">Una vez creados, los paquetes son independientes y portátiles; se pueden instalar desde un stick USB.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-119">Once built, the packages are self-contained and portable; they can be installed from a USB stick.</span></span>  <span data-ttu-id="ed8d2-120">Los paquetes se firman criptográficamente para asegurarse de que se originan en la entidad que notifican.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-120">The packages are cryptographically signed to ensure they originate from the party they claim.</span></span>

<span data-ttu-id="ed8d2-121">El núcleo de un CNAB es un archivo denominado `bundle.json`.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-121">The core of a CNAB is a file called `bundle.json`.</span></span> <span data-ttu-id="ed8d2-122">Este archivo define el contenido de la agrupación, se terraform o imágenes o cualquier otro elemento.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-122">This file defines the contents of the bundle, be they Terraform or images or anything else.</span></span> <span data-ttu-id="ed8d2-123">En la figura 11-9 se define un CNAB que invoca algunos terraform.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-123">Figure 11-9 defines a CNAB that invokes some Terraform.</span></span> <span data-ttu-id="ed8d2-124">No obstante, tenga en cuenta que en realidad se define una imagen de invocación que se usa para invocar terraform.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-124">Notice, however, that it actually defines an invocation image that is used to invoke the Terraform.</span></span> <span data-ttu-id="ed8d2-125">Cuando se empaqueta, el archivo de Docker que se encuentra en el directorio *CNAB* se integra en una imagen de Docker, que se incluirá en la agrupación.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-125">When packaged up, the Docker file that is located in the *cnab* directory is built into a Docker image, which will be included in the bundle.</span></span> <span data-ttu-id="ed8d2-126">Tener terraform instalado dentro de un contenedor de Docker en el paquete significa que los usuarios no necesitan tener terraform instalado en su equipo para ejecutar la agrupación.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-126">Having Terraform installed inside a Docker container in the bundle means that users don't need to have Terraform installed on their machine to run the bundling.</span></span>

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

<span data-ttu-id="ed8d2-127">**Figura 11-13** : un archivo de terraform de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed8d2-127">**Figure 11-13** - An example Terraform file</span></span>

<span data-ttu-id="ed8d2-128">`bundle.json` También define un conjunto de parámetros que se pasan en terraform.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-128">The `bundle.json` also defines a set of parameters that are passed down into the Terraform.</span></span> <span data-ttu-id="ed8d2-129">La parametrización de la agrupación permite la instalación en diversos entornos diferentes.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-129">Parameterization of the bundle allows for installation in a variety of different environments.</span></span>

<span data-ttu-id="ed8d2-130">El formato CNAB también es flexible, lo que permite su uso en cualquier nube.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-130">The CNAB format is also flexible, allowing it to be used against any cloud.</span></span> <span data-ttu-id="ed8d2-131">Incluso se puede usar en soluciones locales como [OpenStack](https://www.openstack.org/).</span><span class="sxs-lookup"><span data-stu-id="ed8d2-131">It can even be used against on-premises solutions such as [OpenStack](https://www.openstack.org/).</span></span>

## <a name="devops-decisions"></a><span data-ttu-id="ed8d2-132">Decisiones de DevOps</span><span class="sxs-lookup"><span data-stu-id="ed8d2-132">DevOps Decisions</span></span>

<span data-ttu-id="ed8d2-133">Hay tantas herramientas excelentes en el espacio de DevOps estos días, así como libros y documentos más fantásticos sobre cómo hacerlo correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-133">There are so many great tools in the DevOps space these days and even more fantastic books and papers on how to succeed.</span></span> <span data-ttu-id="ed8d2-134">Un libro favorito para empezar en el recorrido de DevOps es [el proyecto Phoenix](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), que sigue la transformación de una empresa ficticia de NOOP a DevOps.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-134">A favorite book to get started on the DevOps journey is [The Phoenix Project](https://www.oreilly.com/library/view/the-phoenix-project/9781457191350/), which follows the transformation of a fictional company from NoOps to DevOps.</span></span> <span data-ttu-id="ed8d2-135">Lo único que hay que hacer es que DevOps ya no sea un "bonito" cuando se implementen aplicaciones nativas complejas en la nube.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-135">One thing is for certain: DevOps is no longer a "nice to have" when deploying complex, Cloud Native Applications.</span></span> <span data-ttu-id="ed8d2-136">Es un requisito y debe planearse y reescribirse al principio de cualquier proyecto.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-136">It's a requirement and should be planned for and resourced at the start of any project.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ed8d2-137">[Anterior](infrastructure-as-code.md)
>[Siguiente](summary.md)</span><span class="sxs-lookup"><span data-stu-id="ed8d2-137">[Previous](infrastructure-as-code.md)
[Next](summary.md)</span></span>
