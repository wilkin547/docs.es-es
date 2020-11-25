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
ms.openlocfilehash: 791bd2754a96b97a38e2509c0c61a644324857cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716959"
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
|[ICoreClrDebugTarget::EnumProcesses (Método)](icoreclrdebugtarget-enumprocesses-method.md)|Enumera los procesos que se ejecutan en un equipo remoto.|  
|[ICoreClrDebugTarget::EnumRuntimes (Método)](icoreclrdebugtarget-enumruntimes-method.md)|Enumera Common Language Runtime (CLR) en el proceso especificado de un equipo remoto.|  
|[ICoreClrDebugTarget::FreeMemory (Método)](icoreclrdebugtarget-freememory-method.md)|Libera la memoria asignada por los métodos de enumeración de esta clase.|  
  
## <a name="remarks"></a>Comentarios  

 Actualmente, esta funcionalidad solo se admite para depurar un destino de aplicación basado en Silverlight que se ejecute en un equipo remoto de Macintosh.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteca:** mscordbi_macx86.dll  
  
 **.NET Framework versiones:** 3,5 SP1  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugRemoteTarget (Interfaz)](icordebugremotetarget-interface.md)
- [ICorDebug (Interfaz)](icordebug-interface.md)

- [Interfaces para depuración](debugging-interfaces.md)
