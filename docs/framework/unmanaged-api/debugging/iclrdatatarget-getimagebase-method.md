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
ms.openlocfilehash: fed643ae52f50b1b8cd134880c644c8941da6f56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122873"
---
# <a name="iclrdatatargetgetimagebase-method"></a>ICLRDataTarget::GetImageBase (Método)
Obtiene la dirección de memoria base de la imagen especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `imagePath`  
 de Nombre de archivo de la imagen, incluida su ruta de acceso.  
  
 `baseAddress`  
 enuncia Un puntero a un CLRDATA_ADDRESS que almacena la dirección base de la imagen.  
  
## <a name="remarks"></a>Comentarios  
 El nombre del archivo de imagen puede tener o no una ruta de acceso. Si se especifica una ruta de acceso, la coincidencia se realiza en toda la ruta de acceso; de lo contrario, la búsqueda de coincidencias se realiza solo en el nombre de archivo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl, ClrData. h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRDataTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
