---
title: ICLRDataTarget::GetImageBase (Método)
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e823911280f52e16c745c9c77fe17b49bd35dc0b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129836"
---
# <a name="iclrdatatargetgetimagebase-method"></a>ICLRDataTarget::GetImageBase (Método)
Obtiene la dirección de memoria de base de la imagen especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `imagePath`  
 [in] El nombre de archivo de la imagen, incluida su ruta de acceso.  
  
 `baseAddress`  
 [out] Un puntero a CLRDATA_ADDRESS que almacena la dirección de la imagen base.  
  
## <a name="remarks"></a>Comentarios  
 El nombre de archivo de imagen puede tener o no una ruta de acceso. Si se especifica una ruta de acceso, la búsqueda de coincidencias se realiza en la ruta de acceso completa; en caso contrario, la coincidencia se realiza solo en el nombre de archivo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: ClrData.idl, ClrData.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
