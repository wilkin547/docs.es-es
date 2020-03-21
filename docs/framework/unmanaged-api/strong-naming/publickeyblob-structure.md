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
ms.openlocfilehash: 3b00bf8295a635871bd7263928ff21c97053cc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176960"
---
# <a name="publickeyblob-structure"></a>PublicKeyBlob (Estructura)
Representa, en formato binario, la clave pública de un par de claves pública y privada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`SigAlgId`|Identificador del algoritmo de firma `ALG_ID`(de tipo , tal como se define en WinCrypt.h) de la clave pública.|  
|`HashAlgId`|Identificador del algoritmo hash (de tipo `ALG_ID`, tal como se define en WinCrypt.h) de la clave pública.|  
|`cbPublicKey`|La longitud de la clave en bytes.|  
|`PublicKey`|Matriz de bytes de longitud variable que contiene el valor de clave en el formato devuelto por CryptoAPI.|  
  
## <a name="remarks"></a>Observaciones  
 `PublicKeyBlob` [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)y otras funciones de nombre seguro usan la estructura para representar la clave pública de un par de claves pública y privada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [StrongNameGetPublicKey (Función)](strongnamegetpublickey-function.md)
- [StrongNameSignatureGeneration (Función)](strongnamesignaturegeneration-function.md)
