---
title: StrongNameGetBlobFromImage (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b136e1fa480e53bcacfd9ea832d1dc4d1bd69f74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162787"
---
# <a name="strongnamegetblobfromimage-function"></a>StrongNameGetBlobFromImage (Función)
Obtiene una representación binaria de la imagen de ensamblado en la dirección de memoria especificada.  
  
 Esta función está desusada. Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pbBase`  
 [in] La dirección de memoria del manifiesto del ensamblado asignado.  
  
 `dwLength`  
 [in] El tamaño, en bytes, de la imagen en `pbBase`.  
  
 `pbBlob`  
 [in] Un búfer que contiene la representación binaria de la imagen.  
  
 `pcbBlob`  
 [in, out] El solicita el tamaño máximo, en bytes, de `pbBlob`. Cuando se devuelve, el tamaño real, en bytes, de `pbBlob`.  
  
## <a name="return-value"></a>Valor devuelto  
 `true` Cuando se finaliza correctamente; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Si el `StrongNameGetBlobFromImage` función no se completa correctamente, llame a la [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) función para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: StrongName.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [Método StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [ICLRStrongName (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
