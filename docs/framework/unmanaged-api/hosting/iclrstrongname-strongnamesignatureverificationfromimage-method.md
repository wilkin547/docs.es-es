---
title: "ICLRStrongName::StrongNameSignatureVerificationFromImage (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f312e1eade6de57df9660a349570398d9cd912b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a>ICLRStrongName::StrongNameSignatureVerificationFromImage (Método)
Comprueba que un ensamblado que ya se ha asignado a la memoria es válido para la clave pública asociada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT StrongNameSignatureVerificationFromImage (  
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
 `S_OK`Si el método se completó correctamente; en caso contrario, un valor HRESULT que indica un error (vea [valores HRESULT comunes](http://go.microsoft.com/fwlink/?LinkId=213878) para obtener una lista).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRStrongName (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
