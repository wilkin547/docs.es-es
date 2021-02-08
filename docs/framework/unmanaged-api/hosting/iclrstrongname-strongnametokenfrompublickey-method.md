---
description: 'Más información sobre: ICLRStrongName:: StrongNameTokenFromPublicKey ((método)'
title: ICLRStrongName::StrongNameTokenFromPublicKey (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: de245b151e5ca016a00793a8901c0fd990a3f804
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789750"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a>ICLRStrongName::StrongNameTokenFromPublicKey (Método)

Obtiene un token que representa una clave pública. Un token de nombre seguro es la forma abreviada de una clave pública.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pbPublicKeyBlob`  
 de Estructura de tipo [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) que contiene la parte pública del par de claves utilizado para generar la firma de nombre seguro.  
  
 `cbPublicKeyBlob`  
 de Tamaño, en bytes, de `pbPublicKeyBlob` .  
  
 `ppbStrongNameToken`  
 enuncia El token de nombre seguro correspondiente a la clave pasada `pbPublicKeyBlob` . El Common Language Runtime asigna la memoria en la que se va a devolver el token. El llamador debe liberar esta memoria mediante el método [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .  
  
 `pcbStrongNameToken`  
 enuncia Tamaño, en bytes, del token de nombre seguro devuelto.  
  
## <a name="return-value"></a>Valor devuelto  

 `S_OK` Si el método se completó correctamente; de lo contrario, un valor HRESULT que indica un error (vea [Valores HRESULT comunes](/windows/win32/seccrypto/common-hresult-values) para una lista).  
  
## <a name="remarks"></a>Observaciones  

 Un token de nombre seguro es la forma abreviada de una clave pública que se usa para ahorrar espacio al almacenar información de clave en los metadatos. En concreto, se usan tokens de nombre seguro en las referencias de ensamblado para hacer referencia al ensamblado dependiente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en mscoree.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md)
- [PublicKeyBlob (Estructura)](../strong-naming/publickeyblob-structure.md)
- [ICLRStrongName (Interfaz)](iclrstrongname-interface.md)
