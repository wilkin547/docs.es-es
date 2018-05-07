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
ms.openlocfilehash: b736e58a1a48a2bb4492b6b8ff58af1567babcf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>ICLRStrongName::StrongNameGetPublicKey (Método)
Obtiene la clave pública de un par de claves pública y privada. El par de claves puede especificarse como un nombre de contenedor de claves dentro de un proveedor de servicios criptográficos (CSP) o como una colección de bytes sin formato.  
  
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
 [in] El nombre del contenedor de claves que contiene el par de claves pública y privada. Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido dentro del CSP. En este caso, el [ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) método extrae la clave pública del par de claves que se almacenan en el contenedor.  
  
 Si `pbKeyBlob` no es null, se supone que el par de claves para poder estar contenidos en la clave objeto binario grande (BLOB).  
  
 Las claves deben ser de 1024 bits Rivest-Shamir-Adleman (RSA) claves de firma. Ningún otro tipo de claves se admite en este momento.  
  
 `pbKeyBlob`  
 [in] Un puntero al par de claves pública y privada. Este par está en el formato creado por Win32 `CryptExportKey` función. Si `pbKeyBlob` es null, el contenedor de claves especificado por `szKeyContainer` se supone que contiene el par de claves.  
  
 `cbKeyBlob`  
 [in] El tamaño, en bytes, de `pbKeyBlob`.  
  
 `ppbPublicKeyBlob`  
 [out] La clave pública BLOB devuelta. El `ppbPublicKeyBlob` parámetro es asignado por common language runtime y se devuelve al llamador. El llamador debe liberar la memoria mediante el uso de la [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método.  
  
 `pcbPublicKeyBlob`  
 [out] El tamaño de la clave pública devuelta BLOB.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).  
  
## <a name="remarks"></a>Comentarios  
 La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [StrongNameTokenFromPublicKey (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [PublicKeyBlob (estructura)](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
