---
description: 'Más información acerca de: PublicKeyBlob (estructura)'
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
ms.openlocfilehash: 94c1ea3d5a41bbb8941658e87f97cd6d6336187a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736504"
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`SigAlgId`|Identificador del algoritmo de firma (de tipo `ALG_ID` , tal y como se define en WinCrypt. h) de la clave pública.|  
|`HashAlgId`|Identificador del algoritmo hash (de tipo `ALG_ID` , tal y como se define en WinCrypt. h) de la clave pública.|  
|`cbPublicKey`|Longitud de la clave en bytes.|  
|`PublicKey`|Matriz de bytes de longitud variable que contiene el valor de clave en el formato devuelto por la CryptoAPI.|  
  
## <a name="remarks"></a>Observaciones  

 `PublicKeyBlob` [StrongNameGetPublicKey (](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration (](strongnamesignaturegeneration-function.md)y otras funciones de nombre seguro utilizan la estructura para representar la clave pública de un par de claves pública y privada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameGetPublicKey (Función)](strongnamegetpublickey-function.md)
- [StrongNameSignatureGeneration (Función)](strongnamesignaturegeneration-function.md)
