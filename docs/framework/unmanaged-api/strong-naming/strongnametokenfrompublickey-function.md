---
title: StrongNameTokenFromPublicKey (Función)
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbfd3ae32f4d3033894fdaf6b1bcc880c324e928
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219803"
---
# <a name="strongnametokenfrompublickey-function"></a>StrongNameTokenFromPublicKey (Función)
Obtiene un token que representa una clave pública. Un token de nombre seguro es la forma abreviada de una clave pública.  
  
 Esta función está desusada. Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbPublicKeyBlob`  
 [in] Una estructura de tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.  
  
 `cbPublicKeyBlob`  
 [in] El tamaño, en bytes, de `pbPublicKeyBlob`.  
  
 `ppbStrongNameToken`  
 [out] Pasa el token de nombre seguro correspondiente a la clave `pbPublicKeyBlob`. Common language runtime asigna la memoria en el que se va a devolver el token. El llamador debe liberar esta memoria utilizando la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función.  
  
 `pcbStrongNameToken`  
 [out] El tamaño, en bytes, del token de nombre seguro devuelto.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` Cuando se finaliza correctamente; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Un token de nombre seguro es la forma abreviada de una clave pública utilizada para ahorrar espacio al almacenar la información de clave en los metadatos. En concreto, los tokens de nombre seguro se usan en las referencias de ensamblado para hacer referencia al ensamblado dependiente.  
  
 Si el `StrongNameTokenFromPublicKey` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: StrongName.h  
  
 **Biblioteca:** Incluye como recurso en mscoree.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Método StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob (Estructura)](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
