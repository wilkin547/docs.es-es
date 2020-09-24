---
title: Configuración centralizada
description: Centralizar la configuración de aplicaciones nativas en la nube con la configuración de App de Azure y el almacén de AzureKey.
ms.date: 05/13/2020
ms.openlocfilehash: 0d40c5b2d70f30beb17489dfd55900f7c5fc1a75
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160884"
---
# <a name="centralized-configuration"></a>Configuración centralizada

A diferencia de una aplicación monolítica en la que todo se ejecuta dentro de una única instancia, una aplicación nativa en la nube se compone de servicios independientes distribuidos entre máquinas virtuales, contenedores y regiones geográficas. La administración de los valores de configuración para docenas de servicios interdependientes puede resultar complicada. Las copias duplicadas de los valores de configuración en diferentes ubicaciones es propensa a errores y difíciles de administrar. La configuración centralizada es un requisito fundamental para las aplicaciones distribuidas nativas en la nube.

Como se describe en el [capítulo 1](introduction.md), las recomendaciones de la aplicación de doce factores requieren una separación estricta entre el código y la configuración. La configuración se debe almacenar externamente desde la aplicación y se puede leer según sea necesario. El almacenamiento de valores de configuración como constantes o valores literales en el código es una infracción. Muchos servicios de la misma aplicación suelen usar los mismos valores de configuración. Además, debemos admitir los mismos valores en varios entornos, como desarrollo, pruebas y producción. La práctica recomendada es almacenarlas en un almacén de configuración centralizado.

La nube de Azure presenta varias opciones excelentes.

## <a name="azure-app-configuration"></a>Azure App Configuration

[App de Azure configuración](/azure/azure-app-configuration/overview) es un servicio de Azure totalmente administrado que almacena la configuración no secreta en una ubicación segura y centralizada. Los valores almacenados se pueden compartir entre varios servicios y aplicaciones.

El servicio es fácil de usar y proporciona varias ventajas:

- Asignaciones y representaciones de claves/valores flexibles
- Etiquetado con etiquetas de Azure
- Interfaz de usuario dedicada para administración
- Cifrado de información confidencial
- Consultas y recuperación por lotes

La configuración de App de Azure mantiene los cambios realizados en la configuración de clave-valor durante siete días. La característica de instantánea de un momento dado permite reconstruir el historial de una configuración e incluso revertirla para una implementación con errores.

La configuración de la aplicación almacena automáticamente en caché cada configuración para evitar demasiadas llamadas al almacén de configuración. La operación de actualización espera hasta que el valor de una opción almacenada en la caché expira y, después, actualiza ese valor, incluso aunque este haya cambiado ya en el almacén de configuración. El tiempo de expiración predeterminado de la memoria caché es de 30 segundos. Puede invalidar la hora de expiración.

La configuración de la aplicación cifra todos los valores de configuración en tránsito y en reposo. Los nombres de clave y las etiquetas se usan como índices para recuperar los datos de configuración y no se cifran.

Aunque la configuración de la aplicación proporciona seguridad protegida, Azure Key Vault sigue siendo el mejor lugar para almacenar los secretos de la aplicación. Key Vault proporciona cifrado de nivel de hardware, directivas de acceso pormenorizadas y operaciones de administración como la rotación de certificados. Puede crear valores de configuración de aplicaciones que hagan referencia a secretos almacenados en un Key Vault.

## <a name="azure-key-vault"></a>Azure Key Vault

Key Vault es un servicio administrado para almacenar y obtener acceso a secretos de forma segura. Un secreto es todo aquello a lo cual se desea controlar estrechamente el acceso, como certificados, contraseñas o claves de API. Un almacén es un grupo lógico de secretos.

Key Vault reduce en gran medida las posibilidades de que se puedan filtrar por accidente los secretos. Cuando usan Key Vault, los desarrolladores de aplicaciones ya no tienen que almacenar la información de seguridad en su aplicación. Esta práctica elimina la necesidad de almacenar esta información dentro del código. Por ejemplo, puede que una aplicación necesite conectarse a una base de datos. En lugar de almacenar la cadena de conexión en el código de la aplicación, puede almacenarla de forma segura en Key Vault.

Las aplicaciones pueden acceder de manera protegida a la información que necesitan a través de URI. Estos URI permiten que las aplicaciones recuperen versiones específicas de un secreto. No es necesario escribir código personalizado para proteger la información secreta almacenada en Key Vault.

El acceso a Key Vault requiere la autenticación y autorización adecuadas del llamador. Normalmente, cada microservicio nativo de la nube usa una combinación de ClientId/ClientSecret. Es importante mantener estas credenciales fuera del control de código fuente. Un procedimiento recomendado es establecerlos en el entorno de la aplicación. El acceso directo a Key Vault desde AKS se puede lograr mediante [key Vault FlexVolume](https://github.com/Azure/kubernetes-keyvault-flexvol).

## <a name="configuration-in-eshop"></a>Configuración en eShop

La aplicación eShopOnContainers incluye los archivos de configuración de la aplicación local con cada microservicio. Estos archivos se protegen en el control de código fuente, pero no incluyen secretos de producción, como cadenas de conexión o claves de API. En producción, se puede sobrescribir la configuración individual con variables de entorno por servicio. Insertar secretos en variables de entorno es una práctica común para las aplicaciones hospedadas, pero no proporciona un almacén de configuración central. Para admitir la administración centralizada de las opciones de configuración, cada microservicio incluye una configuración para alternar entre el uso de la configuración local o la configuración de Azure Key Vault.

## <a name="references"></a>Referencias

- [Arquitectura de eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Architecture)
- [Orquestación de microservicios y aplicaciones de varios contenedores para una alta escalabilidad y disponibilidad](../microservices/architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
- [Azure API Management](/azure/api-management/api-management-key-concepts)
- [Información general de Azure SQL Database](/azure/sql-database/sql-database-technical-overview)
- [Azure Cache for Redis](https://azure.microsoft.com/services/cache/)
- [API de Azure Cosmos DB para MongoDB](/azure/cosmos-db/mongodb-introduction)
- [Azure Service Bus](/azure/service-bus-messaging/service-bus-messaging-overview)
- [Introducción a Azure Monitor](/azure/azure-monitor/overview)
- [eShopOnContainers: creación de un clúster de Kubernetes en AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Deploy-to-Azure-Kubernetes-Service-(AKS)#create-kubernetes-cluster-in-aks)
- [eShopOnContainers: Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/Azure-Dev-Spaces)
- [Azure Dev Spaces](/azure/dev-spaces/about)

>[!div class="step-by-step"]
>[Anterior](deploy-eshoponcontainers-azure.md)
>[Siguiente](scale-applications.md)
