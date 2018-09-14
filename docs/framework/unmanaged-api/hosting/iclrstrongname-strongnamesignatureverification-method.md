---
title: ICLRStrongName::StrongNameSignatureVerification (Método)
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49041031742332fbc275a9dbde91e640eb428c28
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "44756619"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a>ICLRStrongName::StrongNameSignatureVerification (Método)
Obtiene un valor que indica si el manifiesto del ensamblado en la ruta de acceso proporcionada contiene una firma de nombre seguro, que se comprueba según las marcas especificadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `wszFilePath`  
 [in] La ruta de acceso al archivo ejecutable portable (.dll o .exe) del ensamblado comprobar.  
  
 `dwInFlags`  
 [in] Marcas para modificar el comportamiento de comprobación. Se admiten los siguientes valores:  
  
-   `SN_INFLAG_FORCE_VER` (0 x 00000001) - fuerza la comprobación incluso si es necesario invalidar la configuración del registro.  
  
-   `SN_INFLAG_INSTALL` (0 x 00000002): Especifica que se trata de la primera vez que se comprueba el manifiesto.  
  
-   `SN_INFLAG_ADMIN_ACCESS` (0 x 00000004): Especifica que la memoria caché permitirá el acceso únicamente a los usuarios que tienen privilegios administrativos.  
  
-   `SN_INFLAG_USER_ACCESS` (0 x 00000008): Especifica que el ensamblado será accesible solo para el usuario actual.  
  
-   `SN_INFLAG_ALL_ACCESS` (0 x 00000010): Especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.  
  
-   `SN_INFLAG_RUNTIME` (0 x 80000000): reservado para la depuración interna.  
  
 `pdwOutFlags`  
 [out] Marcas que indican si se ha comprobado la firma de nombre seguro. Se admite el siguiente valor:  
  
-   `SN_OUTFLAG_WAS_VERIFIED` (0 x 00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  
 `S_OK` Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (consulte [valores HRESULT comunes](https://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [StrongNameSignatureVerificationEx (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
