---
title: ICLRStrongName::StrongNameKeyGen (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d925e30786c742708f345fc23f14c79521cbc6f3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519957"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a>ICLRStrongName::StrongNameKeyGen (Método)
Crea un nuevo par de claves pública y privada para su uso de nombre seguro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `wszKeyContainer`  
 [in] El nombre del contenedor de claves solicitado. `wszKeyContainer` debe ser una cadena vacía o null para generar un nombre temporal.  
  
 `dwFlags`  
 [in] Un valor que especifica si se debe abandonar la clave registrada. Se admiten los siguientes valores:  
  
-   0 x 00000000: se usa cuando `wszKeyContainer` es nulo para generar un nombre de contenedor de claves temporal.  
  
-   0 x 00000001 (`SN_LEAVE_KEY`): Especifica que se debe registrar la clave izquierda.  
  
 `ppbKeyBlob`  
 [out] El par de claves pública y privada devuelto.  
  
 `pcbKeyBlob`  
 [out] El tamaño, en bytes, de `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).  
  
## <a name="remarks"></a>Comentarios  
 El [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) método crea una clave de 1024 bits. Después de recupera la clave, debe llamar a la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) método para liberar la memoria asignada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [StrongNameKeyGenEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
