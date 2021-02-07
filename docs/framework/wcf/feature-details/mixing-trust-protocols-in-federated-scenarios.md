---
description: Más información acerca de cómo combinar protocolos de confianza en escenarios federados
title: Combinación de protocolos de confianza en escenarios federados
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: f882b3728ed791f611a9f71f32840e68d8e17a1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733728"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a>Combinación de protocolos de confianza en escenarios federados

Puede haber situaciones en las que los clientes federados se comuniquen con un servicio y un servicio de tokens de seguridad (STS) que no tengan la misma versión de confianza. El WSDL del servicio puede contener una aserción `RequestSecurityTokenTemplate` con elementos WS-Trust que sean de versiones diferentes que las de STS. En tales casos, un cliente de Windows Communication Foundation (WCF) convierte los elementos WS-Trust recibidos de `RequestSecurityTokenTemplate` para que coincidan con la versión de confianza de STS. WCF controla las versiones de confianza no coincidentes solo para los enlaces estándar. Todos los parámetros de algoritmo estándar reconocidos por WCF forman parte del enlace estándar. En este tema se describe el comportamiento de WCF con varias configuraciones de confianza entre el servicio y el STS.  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a>RP Feb 2005 y STS Feb 2005  

 El WSDL de Usuario de confianza (RP) contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 El archivo de configuración del cliente contiene una lista de parámetros.  
  
 WCF no puede diferenciar entre los parámetros de cliente y de servicio; agrega todos los parámetros y los envía en el `RequestSecurityTokenTemplate` (RST).  
  
## <a name="rp-trust-13-and-sts-trust-13"></a>RP Trust 1.3 y STS Trust 1.3  

 El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 El archivo de configuración del cliente tiene un elemento `secondaryParameters` que contiene los parámetros especificados por RP.  
  
 WCF quita los `EncryptionAlgorithm` `CanonicalizationAlgorithm` elementos, y `KeyWrapAlgorithm` del elemento de nivel superior bajo el RST si están presentes dentro del `SecondaryParameters` elemento. WCF anexa el `SecondaryParameters` elemento al RST de salida sin modificar.  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a>RP Trust Feb 2005 y STS Trust 1.3  

 El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 El archivo de configuración del cliente contiene una lista de parámetros.  
  
 En el archivo de configuración del cliente, WCF no puede diferenciar entre los parámetros de servicio y de cliente. Por lo tanto, WCF convierte todos los parámetros en un espacio de nombres de la versión de confianza 1,3.  
  
 WCF controla los `KeyType` `KeySize` elementos, y `TokenType` como se indica a continuación:  
  
- Descargue el WSDL, cree el enlace y asigne `KeyType`, `KeySize` y `TokenType` de los parámetros RP. A continuación se genera el archivo de configuración del cliente.  
  
- Ahora, el cliente puede cambiar cualquier parámetro del archivo de configuración.  
  
- Durante el tiempo de ejecución, WCF copia todos los parámetros especificados en la `AdditionalTokenParameters` sección del archivo de configuración del cliente `KeyType` , excepto, `KeySize` y `TokenType` , porque estos parámetros se tienen en cuenta durante la generación del archivo de configuración.  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a>RP Trust 1.3 y STS Trust Feb 2005  

 El WSDL de RP contiene los elementos siguientes en la sección `RequestSecurityTokenTemplate`:  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 El archivo de configuración del cliente tiene un elemento `secondaryParamters` que contiene los parámetros especificados por RP.  
  
 WCF copia todos los parámetros especificados en la `SecondaryParameters` sección en el elemento RST de nivel superior, pero no los convierte en el espacio de nombres 2005 WS-Trust.
