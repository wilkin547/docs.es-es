---
title: "CertTimestampAuthenticodeLicense (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CertTimestampAuthenticodeLicense
api_location: clr.dll
api_type: DLLExport
ms.assetid: d468325a-21c5-43ce-8567-84e342b22308
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ec863e9accbd2156b6eeed5857ff86075cf0a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="certtimestampauthenticodelicense-function"></a>CertTimestampAuthenticodeLicense (Función)
Aplica marcas de hora a una licencia Authenticode XrML.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CertTimestampAuthenticodeLicense (  
    [in]  PCRYPT_DATA_BLOB   pSignedLicenseBlob,  
    [in]  LPCWSTR            pwszTimestampURI,  
    [out] PCRYPT_DATA_BLOB   pTimestampSignatureBlob  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pSignedLicenseBlob`  
 [in] Licencia Authenticode XrML firmada a la que se va a aplicar la marca de hora. Consulte la [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) estructura.  
  
 `pwszTimestampURI`  
 [in] URI del servidor de marca de hora.  
  
 `pTimestampSignatureBlob`  
 [out] Puntero a CRYPT_DATA_BLOB para recibir la firma de marca de hora con codificación base64. Es responsabilidad del llamante liberar `pTimestampSignatureBlob` -> `pbData` con `HepFree()` tras su uso. Consulte la [CRYPTOAPI_BLOB](http://msdn.microsoft.com/library/windows/desktop/aa380238.aspx) estructura.  
  
## <a name="remarks"></a>Comentarios  
 La firma de marca de hora es en realidad un mensaje PKCS #7 SignedData cuyo contenido es el formato binario del SignatureValue de la firma de la licencia. Básicamente, actúa como contrafirma de la licencia.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` si la función se realiza correctamente. De lo contrario, devuelve un código de error.  
  
## <a name="see-also"></a>Vea también  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
