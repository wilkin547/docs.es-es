---
title: "StrongNameSignatureVerificationFromImage (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationFromImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationFromImage
helpviewer_keywords: StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab890451c44b19be6472ae6c7da060ae71612bc5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignatureverificationfromimage-function"></a>StrongNameSignatureVerificationFromImage (Función)
Comprueba que un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.  
  
 Esta función está desusada. Use la [ICLRStrongName::StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pbBase`  
 [in] La dirección virtual relativa del manifiesto del ensamblado asignado.  
  
 `dwLength`  
 [in] El tamaño, en bytes, de la imagen asignada.  
  
 `dwInFlags`  
 [in] Marcas que influyen en el comportamiento de la comprobación. Se admiten los siguientes valores:  
  
-   `SN_INFLAG_FORCE_VER`(0 x 00000001) - fuerza la comprobación aunque sea necesario invalidar la configuración del registro.  
  
-   `SN_INFLAG_INSTALL`(0 x 00000002): Especifica que se trata de la primera comprobación que se realiza en esta imagen.  
  
-   `SN_INFLAG_ADMIN_ACCESS`(0 x 00000004): Especifica que la memoria caché permitirá el acceso únicamente a los usuarios que tienen privilegios administrativos.  
  
-   `SN_INFLAG_USER_ACCESS`(0 x 00000008): Especifica que el ensamblado estará accesible sólo para el usuario actual.  
  
-   `SN_INFLAG_ALL_ACCESS`(0 x 00000010): Especifica que la memoria caché no proporcionará ninguna garantía de restricción de acceso.  
  
-   `SN_INFLAG_RUNTIME`(0 x 80000000) - reservado para la depuración interna.  
  
 `pdwOutFlags`  
 [out] Una marca para obtener información de salida adicional. Se admite el siguiente valor:  
  
-   `SN_OUTFLAG_WAS_VERIFIED`(0 x 00000001): este valor se establece en `false` para especificar que la comprobación se realizó correctamente debido a la configuración del registro.  
  
## <a name="return-value"></a>Valor devuelto  
 `true`Cuando se finaliza correctamente; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Si el `StrongNameSignatureVerificationFromImage` función no se completan correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** StrongName.h  
  
 **Biblioteca:** incluye como recurso en mscoree.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [StrongNameSignatureVerificationFromImage (método)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
