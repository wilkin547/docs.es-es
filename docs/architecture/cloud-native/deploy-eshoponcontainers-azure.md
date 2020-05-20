---
title: Implementación de eShopOnContainers en Azure
description: Implementación de la aplicación eShopOnContainers con Azure Kubernetes Service, Helm y DevSpaces.
ms.date: 05/13/2020
ms.openlocfilehash: 93a2848f095d7593e1e169f4a6c6c1818a76217d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614102"
---
# <a name="deploying-eshoponcontainers-to-azure"></a>Implementación de eShopOnContainers en Azure

La aplicación eShopOnContainers se puede implementar en una variedad de plataformas de Azure. El enfoque recomendado es implementar la aplicación en Azure Kubernetes Services (AKS). Helm, una herramienta de implementación de Kubernetes, está disponible para reducir la complejidad de la implementación. Opcionalmente, los desarrolladores pueden implementar Azure Dev Spaces para Kubernetes con el fin de simplificar el proceso de desarrollo.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Para hospedar eShop en AKS, el primer paso es crear un clúster de AKS. Para ello, puede usar el Azure Portal, que le guiará a través de los pasos necesarios. También puede crear un clúster desde el CLI de Azure, teniendo cuidado de habilitar la Access Control basada en roles (RBAC) y el enrutamiento de la aplicación. En la documentación de eShopOnContainers se detallan los pasos para crear su propio clúster de AKS. Una vez creado, puede tener acceso al clúster y administrarlo desde el panel de Kubernetes.

Ahora puede implementar la aplicación de eShop en el clúster aprovechando Helm y el coparador.

## <a name="deploying-to-azure-kubernetes-service-using-helm"></a>Implementación en Azure Kubernetes Service con Helm

Helm es una herramienta del administrador de paquetes de aplicación que funciona directamente con Kubernetes. Ayuda a definir, instalar y actualizar aplicaciones Kubernetes. Aunque las aplicaciones sencillas se pueden implementar en AKS con scripts de la CLI personalizados o archivos de implementación sencillos, las aplicaciones complejas pueden contener muchos objetos Kubernetes y beneficiarse de Helm.

Con Helm, las aplicaciones incluyen archivos de configuración basados en texto, denominados gráficos Helm, que describen la aplicación y la configuración de forma declarativa en paquetes Helm. Los gráficos usan archivos estándar con formato YAML para describir un conjunto relacionado de recursos de Kubernetes. Se crean versiones junto al código de la aplicación que describen. Los gráficos Helm van desde simple a complejo, en función de los requisitos de la instalación que describen.

Helm se compone de una herramienta de cliente de línea de comandos, que consume gráficos de Helm y inicia comandos en un componente de servidor denominado, con el fin de usar el. El coparador se comunica con la API de Kubernetes para garantizar el aprovisionamiento correcto de las cargas de trabajo en contenedores. Helm se mantiene en la base informática nativa de la nube.

El archivo YAML siguiente presenta una plantilla de Helm:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: {{ .Values.app.svc.marketing }}
  labels:
    app: {{ template "marketing-api.name" . }}
    chart: {{ template "marketing-api.chart" . }}
    release: {{ .Release.Name }}
    heritage: {{ .Release.Service }}
spec:
  type: {{ .Values.service.type }}
  ports:
    - port: {{ .Values.service.port }}
      targetPort: http
      protocol: TCP
      name: http
  selector:
    app: {{ template "marketing-api.name" . }}
    release: {{ .Release.Name }}
```

Observe cómo la plantilla describe un conjunto dinámico de pares clave-valor. Cuando se invoca la plantilla, los valores que se incluyen entre llaves se extraen de otros archivos de configuración basados en YAML.

Encontrará los gráficos de eShopOnContainers Helm en la carpeta/K8S/Helm. En la figura 2-6 se muestra cómo se organizan los distintos componentes de la aplicación en una estructura de carpetas que usa Helm para definir y administrar las implementaciones.

![eShopOnContainers arquitectura de la ](./media/eshoponcontainers-helm-folder.png)
 **figura 2-6**. La carpeta eShopOnContainers Helm

Cada componente individual se instala mediante un `helm install` comando. eShop incluye un script "implementar todo" que recorre los componentes y los instala mediante sus respectivos gráficos de Helm. El resultado es un proceso repetible, con versiones de la aplicación en el control de código fuente, que cualquier persona del equipo puede implementar en un clúster de AKS con un comando de script de una línea.

> Tenga en cuenta que la versión 3 de Helm elimina oficialmente la necesidad del componente de servidor de la caja de la cuenta. Puede encontrar más información sobre esta mejora [aquí](https://medium.com/better-programming/why-is-tiller-missing-in-helm-3-2347c446714).

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Las aplicaciones nativas en la nube pueden crecer rápidamente y grandes, lo que requiere recursos de proceso significativos para ejecutarse. En estos casos, toda la aplicación no se puede hospedar en una máquina de desarrollo (especialmente un portátil). Azure Dev Spaces está diseñado para solucionar este problema mediante AKS. Permite a los desarrolladores trabajar con una versión local de sus servicios mientras se hospeda el resto de la aplicación en un clúster de desarrollo de AKS.

Los desarrolladores comparten una instancia en ejecución (desarrollo) en un clúster de AKS que contiene toda la aplicación en contenedor. Pero usan espacios personales configurados en su equipo para desarrollar sus servicios localmente. Cuando está listo, prueban de un extremo a otro en el clúster de AKS, sin replicar las dependencias. Azure Dev Spaces combina el código del equipo local con los servicios de AKS. Los miembros del equipo pueden ver cómo se comportarán sus cambios en un entorno de AKS real. Los desarrolladores pueden iterar y depurar código directamente en Kubernetes con Visual Studio 2017 o Visual Studio Code.

En la figura 2-7, puede ver que Developer Susie ha implementado una versión actualizada del microservicio Bikes en su espacio de desarrollo. Después, puede probar los cambios mediante una dirección URL personalizada que empiece por el nombre de su espacio (susie.s.dev.myapp.eus.azds.io).

![eShopOnContainers arquitectura de la ](./media/azure-devspaces-one.png)
 **figura 2-7**. Developer Susie implementa su propia versión del microservicio Bikes y la prueba.

Al mismo tiempo, el desarrollador John está personalizando el microservicio de reservas y necesita probar sus cambios. Implementa sus cambios en su propio espacio de desarrollo sin entrar en conflicto con los cambios de Susie como se muestra en la figura 2-8. A continuación, Juan prueba sus cambios con su propia dirección URL, que tiene como prefijo el nombre de su espacio (john.s.dev.myapp.eus.azds.io).

![eShopOnContainers arquitectura de la ](./media/azure-devspaces-two.png)
 **figura 2-8**. El desarrollador John implementa su propia versión del microservicio de reservas y la prueba sin conflictos con otros desarrolladores.

Con Azure Dev Spaces, los equipos pueden trabajar directamente con AKS mientras cambian, implementan y prueban sus cambios de forma independiente. Este enfoque reduce la necesidad de entornos hospedados dedicados independientes, ya que todos los desarrolladores tienen su propio entorno de AKS. Los desarrolladores pueden trabajar con Azure Dev Spaces mediante su CLI o iniciar su aplicación para Azure Dev Spaces directamente desde Visual Studio. [Obtenga más información sobre cómo funciona Azure Dev Spaces y está configurado.](https://docs.microsoft.com/azure/dev-spaces/how-dev-spaces-works)

## <a name="azure-functions-and-logic-apps-serverless"></a>Azure Functions y Logic Apps (sin servidor)

El ejemplo eShopOnContainers incluye compatibilidad con el seguimiento de campañas de marketing en línea. Una función de Azure se usa para realizar un seguimiento de los detalles de la campaña de marketing de un identificador de campaña determinado. En lugar de crear un microservicio completo, una sola función de Azure es más sencilla y suficiente. Azure Functions tienen un modelo de compilación e implementación sencillo, especialmente cuando se configura para ejecutarse en Kubernetes. La implementación de la función se genera mediante scripts mediante plantillas Azure Resource Manager (ARM) y el CLI de Azure. Este servicio de campaña no está orientado al cliente e invoca una sola operación, lo que lo convierte en un excelente candidato para Azure Functions. La función requiere una configuración mínima, que incluye una cadena de conexión de base de datos y la configuración de URI base de la imagen. Configure Azure Functions en el Azure Portal.

>[!div class="step-by-step"]
>[Anterior](map-eshoponcontainers-azure-services.md)
>[Siguiente](centralized-configuration.md)
