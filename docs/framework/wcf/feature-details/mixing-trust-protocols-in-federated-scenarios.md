---
title: Combinación de protocolos de confianza en escenarios federados
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: bca23ba16c69c6d21ed7cf49aaebb8d2ed079f5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33494473"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Combinación de protocolos de confianza en escenarios federados
Puede haber situaciones en las que los clientes federados se comuniquen con un servicio y un servicio de tokens de seguridad (STS) que no tengan la misma versión de confianza. El WSDL del servicio puede contener una aserción `RequestSecurityTokenTemplate` con elementos WS-Trust que sean de versiones diferentes que las de STS. En tales casos, un cliente de Windows Communication Foundation (WCF) convierte los elementos de WS-Trust recibidos de la `RequestSecurityTokenTemplate` para que coincida con el STS de confianza versión. WCF controla las versiones de confianza no coincidentes solo para los enlaces estándares. Todos los parámetros de algoritmo estándar que son reconocidos por WCF forman parte del enlace estándar. En este tema se describe el comportamiento WCF con distintas configuraciones de confianza entre el servicio y el STS.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>RP Feb 2005 y STS Feb 2005  
 El WSDL de Usuario de confianza (RP) contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 El archivo de configuración del cliente contiene una lista de parámetros.  
  
 WCF no puede diferenciar entre los parámetros del cliente y el servicio; Agrega todos los parámetros y los envía en el `RequestSecurityTokenTemplate` (RST).  
  
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
  
 WCF quita el `EncryptionAlgorithm`, `CanonicalizationAlgorithm` y `KeyWrapAlgorithm` elementos desde el elemento de nivel superior bajo el RST si están presentes dentro de la `SecondaryParameters` elemento. WCF anexa el `SecondaryParameters` elemento al RST de salida sin cambios.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>RP Trust Feb 2005 y STS Trust 1.3  
 El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:  
  
-   `CanonicalizationAlgorithm`  
  
-   `EncryptionAlgorithm`  
  
-   `EncryptWith`  
  
-   `SignWith`  
  
-   `KeySize`  
  
-   `KeyType`  
  
 El archivo de configuración del cliente contiene una lista de parámetros.  
  
 Desde el archivo de configuración de cliente WCF no puede diferenciar entre los parámetros del servicio y el cliente. Por lo tanto, WCF convierte todos los parámetros en un espacio de nombres de la versión 1.3 de confianza.  
  
 Identificadores WCF la `KeyType`, `KeySize`, y `TokenType` elementos como se indica a continuación:  
  
-   Descargue el WSDL, cree el enlace y asigne `KeyType`, `KeySize` y `TokenType` de los parámetros RP. A continuación se genera el archivo de configuración del cliente.  
  
-   Ahora, el cliente puede cambiar cualquier parámetro del archivo de configuración.  
  
-   En tiempo de ejecución, WCF copia todos los parámetros especificados en la `AdditionalTokenParameters` sección del archivo de configuración del cliente excepto `KeyType`, `KeySize` y `TokenType`, ya que estos parámetros se tienen en cuenta durante el archivo de configuración generación.  
  
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
  
 WCF copia todos los parámetros especificados en la `SecondaryParameters` sección para el elemento RST de nivel superior, pero no los convierte en el espacio de nombres de WS-Trust de 2005.
