---
description: 'Más información sobre: ICorDebugInternalFrame2:: Getframeaddress ((método)'
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
ms.openlocfilehash: bb745424680c5b9a5277badfbe2d96db46e2e3d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791119"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>ICorDebugInternalFrame2::GetFrameAddress (Método)

Devuelve la dirección de la pila del marco interno.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pAddress`  
 enuncia Puntero a `CORDB_ADDRESS` para el marco interno.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La dirección del marco interno se devolvió correctamente.|  
|E_FAIL|No se pudo devolver la dirección del marco interno.|  
|E_INVALIDARG|`pAddress` es `null`.|  
  
## <a name="remarks"></a>Observaciones  

 El valor devuelto en `pAddress` se puede utilizar para determinar la ubicación del marco interno con respecto a otros marcos de la pila. Incluso en equipos basados en IA-64, el marco interno solo vive en la pila y no hay ningún puntero correspondiente a la memoria auxiliar.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugInternalFrame2 (Interfaz)](icordebuginternalframe2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
