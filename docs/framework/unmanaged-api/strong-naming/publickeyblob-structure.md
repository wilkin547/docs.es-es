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
ms.openlocfilehash: e66196e2bd2cb326ca3f5badc67bcf8d81e5fc3c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799164"
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
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`SigAlgId`|Identificador del algoritmo de firma (de tipo `ALG_ID`, tal y como se define en WinCrypt. h) de la clave pública.|  
|`HashAlgId`|Identificador del algoritmo hash (de tipo `ALG_ID`, tal y como se define en WinCrypt. h) de la clave pública.|  
|`cbPublicKey`|Longitud de la clave en bytes.|  
|`PublicKey`|Matriz de bytes de longitud variable que contiene el valor de clave en el formato devuelto por la CryptoAPI.|  
  
## <a name="remarks"></a>Comentarios  
 [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md) y otras funciones de nombre seguro utilizan la estructura `PublicKeyBlob` para representar la clave pública de un par de claves pública y privada.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: StrongName. h  
  
 **Biblioteca** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameGetPublicKey (Función)](strongnamegetpublickey-function.md)
- [StrongNameSignatureGeneration (Función)](strongnamesignaturegeneration-function.md)
