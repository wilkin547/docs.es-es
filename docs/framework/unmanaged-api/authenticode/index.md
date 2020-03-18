---
title: Authenticode (Referencia de la API no administrada)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 1b8b2222950c75f7f9d2ec2704f722087645cd7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73132464"
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode (Referencia de la API no administrada)
Admite el módulo de creación y verificación de licencias Authenticode XrML.  
  
## <a name="in-this-section"></a>En esta sección  
 [_AxlGetIssuerPublicKeyHash (Función)](axlgetissuerpublickeyhash-function.md)  
 Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.  
  
 [_AxlPublicKeyBlobToPublicKeyToken (Función)](axlpublickeyblobtopublickeytoken-function.md)  
 Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.  
  
 [_AxlRSAKeyValueToPublicKeyToken (Función)](axlrsakeyvaluetopublickeytoken-function.md)  
 Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.  
  
 [CertFreeAuthenticodeSignerInfo (Función)](certfreeauthenticodesignerinfo-function.md)  
 Libera recursos asignados para la estructura AXL_AUTHENTICODE_SIGNER_INFO.  
  
 [CertFreeAuthenticodeTimestamperInfo (Función)](certfreeauthenticodetimestamperinfo-function.md)  
 Libera recursos asignados para la estructura AXL_AUTHENTICODE_TIMESTAMPER_INFO.  
  
 [CertTimestampAuthenticodeLicense (Función)](certtimestampauthenticodelicense-function.md)  
 Aplica marcas de hora a una licencia Authenticode XrML creada por CertCreateAuthenticodeLicense.  
  
 [CertVerifyAuthenticodeLicense (Función)](certverifyauthenticodelicense-function.md)  
 Comprueba la validez de una licencia Authenticode XrML.  
  
 [AXL_AUTHENTICODE_SIGNER_INFO (estructura)](axl-authenticode-signer-info-structure.md)  
 Define la información del firmante de Authenticode.  
  
 [AXL_AUTHENTICODE_TIMESTAMPER_INFO (estructura)](axl-authenticode-timestamper-info-structure.md)  
 Define la información del autor de la marca de hora de Authenticode.  
  
## <a name="see-also"></a>Vea también

- [Referencia de API no administrada](../index.md)
