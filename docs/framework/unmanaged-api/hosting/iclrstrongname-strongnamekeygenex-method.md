---
title: ICLRStrongName::StrongNameKeyGenEx (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b213285b3c533488cfa48198951275925c0e37ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436191"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a>ICLRStrongName::StrongNameKeyGenEx (Método)
Genera un nuevo par de claves pública/privada con el tamaño de clave especificado, para su uso de nombre seguro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `wszKeyContainer`  
 [in] El nombre de contenedor de claves solicitado. `wszKeyContainer` debe ser una cadena no vacía o null para generar un nombre temporal.  
  
 `dwFlags`  
 [in] Un valor que especifica si se debe abandonar la clave registrada. Se admiten los siguientes valores:  
  
-   0 x 00000000: se usa cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.  
  
-   0 x 00000001 (`SN_LEAVE_KEY`)-especifica que la clave debería quedar registrada.  
  
 `dwKeySize`  
 [in] El tamaño solicitado de la clave en bits.  
  
 `ppbKeyBlob`  
 [out] El par de claves pública y privada devuelto.  
  
 `pcbKeyBlob`  
 [out] El tamaño, en bytes, de `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).  
  
## <a name="remarks"></a>Comentarios  
 Las versiones de .NET Framework 1.0 y 1.1 requieren un `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro; la versión 2.0 también admite claves de 2048 bits de.  
  
 Una vez recuperada la clave, debe llamar a la [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método para liberar la memoria asignada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [StrongNameKeyGen (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
