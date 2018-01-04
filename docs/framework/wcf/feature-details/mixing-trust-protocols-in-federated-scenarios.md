---
title: "Combinación de protocolos de confianza en escenarios federados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7031e222b152bfa61e13e0e4a44b5ad9418b07c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Combinación de protocolos de confianza en escenarios federados
Puede haber situaciones en las que los clientes federados se comuniquen con un servicio y un servicio de tokens de seguridad (STS) que no tengan la misma versión de confianza. El WSDL del servicio puede contener una aserción `RequestSecurityTokenTemplate` con elementos WS-Trust que sean de versiones diferentes que las de STS. En estos casos, un cliente de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] convierte los elementos de WS-Trust recibidos de `RequestSecurityTokenTemplate` para que coincida con la versión de confianza del STS. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] controla las versiones de confianza no coincidentes solo para los enlaces estándar. Todos los parámetros de algoritmos estándar que son reconocidos por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] forman parte del enlace estándar. En este tema se describe el comportamiento de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] con distintas configuraciones de confianza entre el servicio y STS.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>RP Feb 2005 y STS Feb 2005  
 El WSDL de Usuario de confianza (RP) contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 El archivo de configuración del cliente contiene una lista de parámetros.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no pueden diferenciar entre los parámetros del servicio y del cliente; agrega todos los parámetros y los envía en `RequestSecurityTokenTemplate` (RST).  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>RP Trust 1.3 y STS Trust 1.3  
 El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 El archivo de configuración del cliente tiene un elemento `secondaryParameters` que contiene los parámetros especificados por RP.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] quita los elementos `EncryptionAlgorithm`, `CanonicalizationAlgorithm` y `KeyWrapAlgorithm` del elemento de nivel superior bajo el RST si están presentes dentro del elemento `SecondaryParameters`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] anexa el elemento `SecondaryParameters` al RST de salida sin modificar.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>RP Trust Feb 2005 y STS Trust 1.3  
 El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 El archivo de configuración del cliente contiene una lista de parámetros.  
  
 A partir del archivo de configuración del cliente, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no pueden diferenciar entre los parámetros del cliente y del servicio. Por consiguiente, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] convierte todos los parámetros a un espacio de nombres de la versión Trust 1.3.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] controla los elementos `KeyType`, `KeySize` y `TokenType` de la manera siguiente:  
  
-   Descargue el WSDL, cree el enlace y asigne `KeyType`, `KeySize` y `TokenType` de los parámetros RP. A continuación se genera el archivo de configuración del cliente.  
  
-   Ahora, el cliente puede cambiar cualquier parámetro del archivo de configuración.  
  
-   Durante el tiempo de ejecución, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copia todos los parámetros especificados en la sección `AdditionalTokenParameters` del archivo de configuración del cliente excepto `KeyType`, `KeySize` y `TokenType`, porque estos parámetros se tienen en cuenta durante la generación del archivo de configuración.  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>RP Trust 1.3 y STS Trust Feb 2005  
 El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
-   `KeyWrapAlgorithm`  
  
 El archivo de configuración del cliente tiene un elemento `secondaryParamters` que contiene los parámetros especificados por RP.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] copia todos los parámetros especificados dentro de la sección `SecondaryParameters` en el elemento RST de nivel superior, pero no los convierte al espacio de nombres WS-Trust de 2005.
