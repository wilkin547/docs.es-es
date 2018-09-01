---
title: ICLRStrongName::StrongNameGetPublicKey (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8d97653a195ec0fc287455079f37b311c3d42e4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43387162"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>ICLRStrongName::StrongNameGetPublicKey (Método)
Obtiene la clave pública de un par de claves pública y privada. El par de claves puede proporcionarse como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin formato.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `szKeyContainer`  
 [in] Nombre del contenedor de claves que contiene el par de claves pública y privada. Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido dentro del CSP. En este caso, el [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) método extrae la clave pública del par de claves almacenado en el contenedor.  
  
 Si `pbKeyBlob` no es null, se supone que el par de claves que se debe incluir en la clave objeto binario grande (BLOB).  
  
 Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) las claves de firma. Se admite ningún otro tipo de claves en este momento.  
  
 `pbKeyBlob`  
 [in] Un puntero a la par de claves pública y privada. Este par está en el formato creado por Win32 `CryptExportKey` función. Si `pbKeyBlob` es null, el contenedor de claves especificado por `szKeyContainer` se supone que contiene el par de claves.  
  
 `cbKeyBlob`  
 [in] El tamaño, en bytes, de `pbKeyBlob`.  
  
 `ppbPublicKeyBlob`  
 [out] La clave pública BLOB devuelta. El `ppbPublicKeyBlob` parámetro asignado por common language runtime y se devuelve al llamador. El llamador debe liberar la memoria utilizando la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método.  
  
 `pcbPublicKeyBlob`  
 [out] El tamaño de la clave pública devuelta BLOB.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).  
  
## <a name="remarks"></a>Comentarios  
 La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [StrongNameTokenFromPublicKey (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [PublicKeyBlob (estructura)](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
