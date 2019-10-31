---
title: ICorDebugCode2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
ms.openlocfilehash: 7f0570b668cc33ca509c8522d1ba35ebcfca2453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125573"
---
# <a name="icordebugcode2-interface"></a>ICorDebugCode2 (Interfaz)

Proporciona métodos que amplían las capacidades de "ICorDebugCode".  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetCodeChunks (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|Obtiene los fragmentos de código de los que está compuesto este objeto de código.|  
|[GetCompilerFlags (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|Obtiene las marcas que especifican las condiciones bajo las que este objeto de código se compiló Just-In-Time (JIT) o se generó usando el generador de imágenes nativas (Ngen.exe).|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugCode3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
