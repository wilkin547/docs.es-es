---
title: Implementación de eShopOnContainers en Azure
description: Implementación de la aplicación eShopOnContainers con Azure Kubernetes Service, Helm y DevSpaces.
ms.date: 06/30/2019
ms.openlocfilehash: 21033cc904dc595193c69f3452ce2522740f8ff6
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840494"
---
# <a name="deploying-eshoponcontainers-to-azure"></a>Implementación de eShopOnContainers en Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

La lógica compatible con la aplicación eShopOnContainers puede ser compatible con Azure mediante una variedad de servicios. El enfoque recomendado es aprovechar Kubernetes con Azure Kubernetes Service (AKS). Esto se puede combinar con la implementación de Helm para garantizar una configuración de infraestructura repetida fácilmente. Opcionalmente, los desarrolladores pueden aprovechar Azure Dev Spaces para Kubernetes como parte de su proceso de desarrollo. Otra opción es hospedar la funcionalidad de la aplicación con características sin servidor de Azure como Azure Functions y Azure Logic Apps.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Si desea hospedar la aplicación eShopOnContainers en su propio clúster de AKS, el primer paso es crear el clúster. Puede hacerlo mediante el Azure Portal, que le guiará a través de los pasos necesarios, o bien puede usar el CLI de Azure, con cuidado para asegurarse de habilitar el Access Control basado en roles (RBAC) y el enrutamiento de la aplicación cuando lo haga. La documentación de eShopOnContainers describe los pasos necesarios para crear su propio clúster de AKS. Una vez creado el clúster, debe habilitar el acceso al panel de Kubernetes, en el que debería poder ir al panel de Kubernetes para administrar el clúster.

Una vez que se ha creado y configurado el clúster, puede implementar la aplicación en él mediante Helm y el uso de la aplicación.

## <a name="deploying-to-azure-kubernetes-service-using-helm"></a>Implementación en Azure Kubernetes Service con Helm

Las implementaciones básicas en AKS pueden usar scripts de la CLI personalizados o archivos de implementación simples, pero las aplicaciones más complejas deben usar una herramienta de administración de dependencias como Helm. Helm se mantiene en la base informática nativa de la nube y le ayuda a definir, instalar y actualizar las aplicaciones de Kubernetes. Helm se compone de un cliente de línea de comandos, Helm, que usa gráficos de Helm, y un componente en clúster, con el fin de utilizarlo. Los gráficos de Helm usan archivos estándar con formato YAML para describir un conjunto relacionado de recursos de Kubernetes y suelen tener versiones junto a la aplicación que describen. Los gráficos Helm van desde simple a complejo, en función de los requisitos de la instalación que describen.

Encontrará los gráficos de eShopOnContainers Helm en la carpeta/K8S/Helm. En la figura 2-6 se muestra cómo se organizan los distintos componentes de la aplicación en una estructura de carpetas que usa Helm para definir y administrar las implementaciones.

![arquitectura de eShopOnContainers](./media/eshoponcontainers-helm-folder.png)
**figura 2-6**. La carpeta eShopOnContainers Helm

Cada componente individual se instala mediante un comando `helm install`. Estos comandos se pueden incluir fácilmente en el script, y eShopOnContainers proporciona un script "implementar todo" que recorre los distintos componentes y los instala mediante sus respectivos gráficos de Helm. El resultado es un proceso repetible, con versiones de la aplicación en el control de código fuente, que cualquier persona del equipo puede implementar en un clúster de AKS con un comando de script de una línea. Especialmente cuando se combina con Azure Dev Spaces, esto facilita a los desarrolladores el diagnóstico y la prueba de sus cambios individuales en sus aplicaciones nativas en la nube basadas en microservicios.

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Azure Dev Spaces ayuda a los desarrolladores individuales a hospedar su propia versión única de los clústeres de AKS en Azure durante el desarrollo. Esto minimiza los requisitos de la máquina local y permite a los miembros del equipo ver rápidamente cómo se comportarán los cambios en un entorno de AKS real. Azure Dev Spaces ofrece una CLI para que los desarrolladores puedan usar para administrar sus espacios de desarrollo y realizar implementaciones en un espacio de desarrollo secundario específico según sea necesario. Se hace referencia a cada espacio de desarrollo secundario mediante un subdominio URL único, que permite implementaciones en paralelo de clústeres modificados para que los desarrolladores individuales puedan evitar conflictos con el trabajo en curso. En la figura 2-7 puede ver cómo Developer Susie ha implementado su propia versión del microservicio Bikes en su espacio de desarrollo. Después, puede probar los cambios mediante una dirección URL personalizada que empiece por el nombre de su espacio (susie.s.dev.myapp.eus.azds.io).

![arquitectura de eShopOnContainers](./media/azure-devspaces-one.png)
**figura 2-7**. Developer Susie implementa su propia versión del microservicio Bikes y la prueba.

Al mismo tiempo, el desarrollador John está personalizando el microservicio de reservas y necesita probar sus cambios. Puede implementar sus cambios en su propio espacio de desarrollo sin entrar en conflicto con los cambios de Susie como se muestra en la figura 2-8. Puede probar sus cambios con su propia dirección URL, que tiene como prefijo el nombre de su espacio (john.s.dev.myapp.eus.azds.io).

![arquitectura de eShopOnContainers](./media/azure-devspaces-two.png)
**figura 2-8**. El desarrollador John implementa su propia versión del microservicio de reservas y la prueba sin conflictos con otros desarrolladores.

Con Azure Dev Spaces, los equipos pueden trabajar directamente con AKS mientras cambian, implementan y prueban sus cambios de forma independiente. Este enfoque reduce la necesidad de entornos hospedados dedicados independientes, ya que todos los desarrolladores tienen su propio entorno de AKS. Los desarrolladores pueden trabajar con Azure Dev Spaces mediante su CLI o iniciar su aplicación para Azure Dev Spaces directamente desde Visual Studio. [Obtenga más información sobre cómo funciona Azure Dev Spaces y está configurado.](https://docs.microsoft.com/azure/dev-spaces/how-dev-spaces-works)

## <a name="azure-functions-and-logic-apps-serverless"></a>Azure Functions y Logic Apps (sin servidor)

El ejemplo eShopOnContainers incluye compatibilidad con el seguimiento de campañas de marketing en línea. Una función de Azure se usa para extraer los detalles de la campaña de marketing de un identificador de campaña determinado. En lugar de crear una aplicación ASP.NET Core completa con este fin, un único punto de conexión de Azure function es más sencillo y suficiente. Azure Functions tienen un modelo de compilación e implementación mucho más sencillo que las aplicaciones de ASP.NET Core completas, especialmente cuando se configura para ejecutarse en Kubernetes. La implementación de la función se genera mediante scripts mediante plantillas Azure Resource Manager (ARM) y el CLI de Azure. El microservicio de detalles de la campaña no está orientado al cliente y no tiene los mismos requisitos que la tienda en línea, por lo que es un buen candidato para Azure Functions. La función requiere que alguna configuración funcione correctamente, como los datos de la cadena de conexión de base de datos y la configuración de URI base de la imagen. Configure Azure Functions en Azure portal.

## <a name="references"></a>Referencias

- [eShopOnContainers: creación de un clúster de Kubernetes en AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#create-kubernetes-cluster-in-aks)
- [eShopOnContainers: Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces)
- [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/about)

>[!div class="step-by-step"]
>[Anterior](map-eshoponcontainers-azure-services.md)
>[Siguiente](centralized-configuration.md)
