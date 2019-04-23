---
title: PublicKeyBlob (Estructura)
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a361e04b6f8f39ec0083471d8cb47d5a29376c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214824"
---
# <a name="publickeyblob-structure"></a>PublicKeyBlob (Estructura)
Representa, en formato binario, la clave pública de un par de claves pública y privada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`SigAlgId`|El identificador del algoritmo de firma (de tipo `ALG_ID`, tal como se define en WinCrypt.h) de la clave pública.|  
|`HashAlgId`|El identificador del algoritmo hash (de tipo `ALG_ID`, tal como se define en WinCrypt.h) de la clave pública.|  
|`cbPublicKey`|La longitud de la clave en bytes.|  
|`PublicKey`|Una matriz de bytes de longitud variable que contiene el valor de clave en el formato devuelto por CryptoAPI.|  
  
## <a name="remarks"></a>Comentarios  
 El `PublicKeyBlob` estructura la usa [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)y otras funciones de nombre seguro para representar la clave pública de un par de claves pública y privada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: StrongName.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameGetPublicKey (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)
- [StrongNameSignatureGeneration (Función)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)
