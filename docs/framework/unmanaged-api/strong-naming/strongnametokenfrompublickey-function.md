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
ms.openlocfilehash: b95c96efeb666f25d04118aa8cb9b0da3a2e7924
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104161"
---
# <a name="strongnametokenfrompublickey-function"></a>StrongNameTokenFromPublicKey (Función)
Obtiene un token que representa una clave pública. Un token de nombre seguro es la forma abreviada de una clave pública.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: StrongNameTokenFromPublicKey (](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbPublicKeyBlob`  
 de Estructura de tipo [PublicKeyBlob](publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.  
  
 `cbPublicKeyBlob`  
 de Tamaño, en bytes, de `pbPublicKeyBlob`.  
  
 `ppbStrongNameToken`  
 enuncia El token de nombre seguro correspondiente a la clave pasada `pbPublicKeyBlob`. El Common Language Runtime asigna la memoria en la que se va a devolver el token. El autor de la llamada debe liberar esta memoria mediante la función [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbStrongNameToken`  
 enuncia Tamaño, en bytes, del token de nombre seguro devuelto.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` cuando se complete correctamente; de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Un token de nombre seguro es la forma abreviada de una clave pública que se usa para ahorrar espacio al almacenar información de clave en los metadatos. En concreto, se usan tokens de nombre seguro en las referencias de ensamblado para hacer referencia al ensamblado dependiente.  
  
 Si la función `StrongNameTokenFromPublicKey` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como recurso en Mscoree. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [StrongNameTokenFromPublicKey (método)](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [StrongNameGetPublicKey (método)](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob (estructura)](publickeyblob-structure.md)
