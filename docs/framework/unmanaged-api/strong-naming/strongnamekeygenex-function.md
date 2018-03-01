---
title: "StrongNameKeyGenEx (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae564f7c4e8333e33b2f2f6229034c3a1396a687
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeygenex-function"></a>StrongNameKeyGenEx (Función)
Genera un nuevo par de claves pública/privada con el tamaño de clave especificado, para su uso de nombre seguro.  
  
 Esta función está desusada. Use la [ICLRStrongName:: StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `wszKeyContainer`  
 [in] El nombre de contenedor de claves solicitado. `wszKeyContainer`debe ser una cadena no vacía o null para generar un nombre temporal.  
  
 `dwFlags`  
 [in] Especifica si se debe abandonar la clave registrada. Se admiten los siguientes valores:  
  
-   0 x 00000000: se usa cuando `wszKeyContainer` es null para generar un nombre de contenedor de claves temporal.  
  
-   0 x 00000001 (`SN_LEAVE_KEY`)-especifica que la clave debería quedar registrada.  
  
 `dwKeySize`  
 [in] El tamaño solicitado de la clave en bits.  
  
 `ppbKeyBlob`  
 [out] El par de claves pública y privada devuelto.  
  
 `pcbKeyBlob`  
 [out] El tamaño, en bytes, de `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`Cuando se finaliza correctamente; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Las versiones de .NET Framework 1.0 y 1.1 requieren un `dwKeySize` de 1024 bits para firmar un ensamblado con un nombre seguro; la versión 2.0 también admite claves de 2048 bits de.  
  
 Una vez recuperada la clave, debe llamar a la [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) función para liberar la memoria asignada.  
  
 Si el `StrongNameKeyGenEx` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** StrongName.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [StrongNameKeyGenEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [StrongNameKeyGen (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
