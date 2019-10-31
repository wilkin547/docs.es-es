---
title: ICoreClrDebugTarget (Interfaz)
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
ms.openlocfilehash: 83afe121b6bf0de3c5542695e38b6605db7a8b6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121815"
---
# <a name="icoreclrdebugtarget-interface"></a>ICoreClrDebugTarget (Interfaz)
Proporciona métodos que controlan los recuentos de referencias, enumeran los procesos y liberan la memoria asociada a un depurador que está asociado a un destino de Silverlight de Macintosh remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ICoreClrDebugTarget::EnumProcesses (método)](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|Enumera los procesos que se ejecutan en un equipo remoto.|  
|[ICoreClrDebugTarget::EnumRuntimes (método)](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|Enumera Common Language Runtime (CLR) en el proceso especificado de un equipo remoto.|  
|[ICoreClrDebugTarget::FreeMemory (método)](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|Libera la memoria asignada por los métodos de enumeración de esta clase.|  
  
## <a name="remarks"></a>Comentarios  
 Actualmente, esta funcionalidad solo se admite para depurar un destino de aplicación basado en Silverlight que se ejecute en un equipo remoto de Macintosh.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteca:** mscordbi_macx86. dll  
  
 **.NET Framework versiones:** 3,5 SP1  
  
## <a name="see-also"></a>Vea también

- [ICorDebugRemoteTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
