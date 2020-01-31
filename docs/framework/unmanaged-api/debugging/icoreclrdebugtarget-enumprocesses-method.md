---
title: ICoreClrDebugTarget::EnumProcesses (Método)
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumProcesses
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumProcesses
helpviewer_keywords:
- remote debugging API [Silverlight]
- EnumProcesses method, ICorClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::EnumProcesses method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: e00fd477-4f49-43d3-bd0e-3094824b1136
topic_type:
- apiref
ms.openlocfilehash: 11b1072b3467f7d0a3f223fbc2151ec9ccf461ad
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790804"
---
# <a name="icoreclrdebugtargetenumprocesses-method"></a>ICoreClrDebugTarget::EnumProcesses (Método)
Enumera los procesos que se ejecutan en un equipo remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumProcesses (  
       [out]  DWORD*                  pcProcs,   
       [out]  CoreClrDebugProcInfo**  ppProcs  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pcProcs`  
 [out] Número de procesos que se devuelve en `ppProcs`. Este valor puede ser 0 (cero).  
  
 `ppProcs`  
 enuncia Matriz de estructuras [coreclrdebugprocinfo (](coreclrdebugprocinfo-structure.md) que representan los procesos que se ejecutan en el equipo remoto.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 Correcto.  
  
 E_OUTOFMEMORY  
 No se puede asignar memoria suficiente para `ppProcs`.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 Otros errores.  
  
## <a name="remarks"></a>Notas  
 Para liberar la memoria asignada por este método, llame al método [ICoreClrDebugTarget:: FreeMemory (](icoreclrdebugtarget-freememory-method.md) .  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Library:** mscordbi_macx86.dll  
  
 **.NET Framework versiones:** 3,5 SP1  
  
## <a name="see-also"></a>Vea también

- [ICoreClrDebugTarget (interfaz)](icoreclrdebugtarget-interface.md)
