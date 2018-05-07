---
title: StrongNameGetPublicKeyEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03e3ff2adc238640034309e0f9eab6e786472631
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="strongnamegetpublickeyex-method"></a>StrongNameGetPublicKeyEx (Método)
Obtiene la clave pública de un par de claves pública y privada y especifica un algoritmo hash y un algoritmo de firma.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwzKeyContainer`  
 [in] El nombre del contenedor de claves que contiene el par de claves pública y privada. Si `pbKeyBlob` es null, `szKeyContainer` debe especificar un contenedor válido en el proveedor de servicios criptográficos (CSP). En este caso, el `StrongNameGetPublicKeyEx` método extrae la clave pública del par de claves que se almacenan en el contenedor.  
  
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
  
 `uHashAlgId`  
 [in] El algoritmo de hash de ensamblado. Vea la sección Comentarios para obtener una lista de valores que se aceptan.  
  
 `uReserved`  
 [in] Reservado para uso futuro; el valor predeterminado es null.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).  
  
## <a name="remarks"></a>Comentarios  
 La clave pública se encuentra en un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) estructura.  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente muestra el conjunto de valores aceptados para el `uHashAlgId` parámetro.  
  
|nombre|Valor|  
|----------|-----------|  
|Ninguna|0|  
|SHA-1|0 x 8004|  
|SHA-256|0x800c|  
|SHA-384|0x800d|  
|SHA-512|0x800e|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [StrongNameTokenFromPublicKey (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [PublicKeyBlob (estructura)](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [StrongNameGetPublicKey (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
