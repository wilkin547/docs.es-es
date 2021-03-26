---
description: 'Más información acerca de: Authenticode (Referencia de la API no administrada)'
title: Authenticode (Referencia de la API no administrada)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 0a4a9b4ba3cc9a5818896508c80bc31073f514e7
ms.sourcegitcommit: 26721a2260deabb3318cc98af8619306711153cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2021
ms.locfileid: "105027849"
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode (Referencia de la API no administrada)

Admite el módulo de creación y verificación de licencias Authenticode XrML.  
  
## <a name="in-this-section"></a>En esta sección  

 [_AxlGetIssuerPublicKeyHash (Función)](axlgetissuerpublickeyhash-function.md)  
 Recupera el hash SHA-1 de la clave pública asociada con la clave privada que se usa para firmar el certificado especificado.  
  
 [_AxlPublicKeyBlobToPublicKeyToken (Función)](axlpublickeyblobtopublickeytoken-function.md)  
 Calcula el token de clave pública del nombre seguro a partir de un formato CSP PUBLICKEYBLOB.  
  
 [Función _AxlRSAKeyValueToPublicKeyToken](axlrsakeyvaluetopublickeytoken-function.md)  
 Convierte un blob Modulus y Exponent en un token de clave pública de nombre seguro.  
  
 [CertFreeAuthenticodeSignerInfo (Función)](certfreeauthenticodesignerinfo-function.md)  
 Libera recursos asignados para la estructura AXL_AUTHENTICODE_SIGNER_INFO.  
  
 [CertFreeAuthenticodeTimestamperInfo (Función)](certfreeauthenticodetimestamperinfo-function.md)  
 Libera recursos asignados para la estructura AXL_AUTHENTICODE_TIMESTAMPER_INFO.  
  
 [CertTimestampAuthenticodeLicense (Función)](certtimestampauthenticodelicense-function.md)  
 Aplica marcas de hora a una licencia Authenticode XrML creada por CertCreateAuthenticodeLicense.  
  
 [CertVerifyAuthenticodeLicense (Función)](certverifyauthenticodelicense-function.md)  
 Comprueba la validez de una licencia Authenticode XrML.  
  
 [AXL_AUTHENTICODE_SIGNER_INFO (Estructura)](axl-authenticode-signer-info-structure.md)  
 Define la información del firmante de Authenticode.  
  
 [AXL_AUTHENTICODE_TIMESTAMPER_INFO (Estructura)](axl-authenticode-timestamper-info-structure.md)  
 Define la información del autor de la marca de hora de Authenticode.  

## <a name="requirements"></a>Requisitos

**Biblioteca**: clr.dll
  
## <a name="see-also"></a>Consulte también

- [Referencia de API no administrada](../index.md)
