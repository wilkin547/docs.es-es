---
title: ICorDebugInternalFrame2::GetFrameAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d088aaaaa80ee3513a37ea0345d720832504c005
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421153"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>ICorDebugInternalFrame2::GetFrameAddress (Método)
Devuelve la dirección de la pila del marco interno.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pAddress`  
 [out] Puntero a la `CORDB_ADDRESS` para el marco interno.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La dirección del marco interno se devolvió correctamente.|  
|E_FAIL|No se pudo devolver la dirección del marco interno.|  
|E_INVALIDARG|El valor de `pAddress` es `null`.|  
  
## <a name="remarks"></a>Comentarios  
 El valor devuelto en `pAddress` puede utilizarse para determinar la ubicación del marco interno en relación con otros marcos de la pila. Incluso en equipos basados en IA-64, el marco interno se mantiene en la pila solo y no hay ningún puntero correspondiente a un almacén de copia de seguridad.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugInternalFrame2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
