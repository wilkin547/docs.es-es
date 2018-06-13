---
title: ICorDebugStringValue Interfaz1
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2814f6164f383c36bb5b8e20ce8996b30eef0f1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421705"
---
# <a name="icordebugstringvalue-interface1"></a>ICorDebugStringValue Interfaz1
Una subclase de ICorDebugHeapValue que se aplica a valores de cadena.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetLength (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|Obtiene el número de caracteres de la cadena que hace referencia esta `ICorDebugStringValue`.|  
|[GetString (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|Obtiene la cadena que hace referencia esta `ICorDebugStringValue`.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
