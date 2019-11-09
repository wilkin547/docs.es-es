---
title: Configuración centralizada
description: La configuración centralizada mediante Azure Key Vault puede facilitar la administración de aplicaciones nativas en la nube.
ms.date: 06/30/2019
ms.openlocfilehash: 4c516b6773d913acd71ff06742302e9766a141e2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841142"
---
# <a name="centralized-configuration"></a>Configuración centralizada

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Las aplicaciones nativas de la nube implican muchos más servicios en ejecución que las aplicaciones monolíticas de una sola instancia tradicionales. La administración de los valores de configuración para docenas de servicios interdependientes puede ser complicada, por lo que a menudo los almacenes de configuración centralizados se implementan para aplicaciones distribuidas.

Como se describe en el [capítulo 1](introduction.md), las recomendaciones de la aplicación de doce factores requieren una separación estricta entre el código y la configuración. Esto significa que el almacenamiento de los valores de configuración como constantes o valores literales en el código es una infracción. Esta recomendación existe porque el mismo código debe usarse en varios entornos, incluidos el desarrollo, la prueba, el almacenamiento provisional y la producción. Sin embargo, es probable que los valores de configuración varíen entre cada uno de estos entornos. Por lo tanto, los valores de configuración deben almacenarse en el propio entorno o el entorno debe almacenar las credenciales en un almacén de configuración centralizado.

La aplicación eShopOnContainers incluye los archivos de configuración de la aplicación local con cada microservicio. Estos archivos se protegen en el control de código fuente, pero no incluyen secretos de producción, como cadenas de conexión o claves de API. En producción, se puede sobrescribir la configuración individual con variables de entorno por servicio. Esta es una práctica común para las aplicaciones hospedadas, pero no proporciona un almacén de configuración central. Para admitir la administración centralizada de las opciones de configuración, cada microservicio incluye una configuración para alternar entre el uso de la configuración local o la configuración de Azure Key Vault.

## <a name="azure-key-vault"></a>Azure Key Vault

Azure Key Vault proporciona almacenamiento seguro de tokens, contraseñas, certificados, claves de API y otros secretos confidenciales. El acceso a Key Vault requiere la autenticación y autorización adecuadas del llamador, que en el caso de los microservicios eShopOnContainers, significa el uso de una combinación de ClientId/ClientSecret. No proteja estas credenciales en el control de código fuente, sino que en el entorno de la aplicación. El acceso directo a Key Vault desde AKS se puede lograr mediante [key Vault FlexVolume](https://github.com/Azure/kubernetes-keyvault-flexvol).

Con la configuración centralizada, la configuración que se aplica a toda la aplicación, como el extremo de registro centralizado, se puede establecer una vez y usar en cada parte de la aplicación distribuida. Aunque los microservicios deben ser independientes entre sí, normalmente habrá algunas dependencias compartidas cuyos detalles de configuración pueden beneficiarse de un almacén de configuración centralizado.

>[!div class="step-by-step"]
>[Anterior](deploy-eshoponcontainers-azure.md)
>[Siguiente](scale-applications.md)
