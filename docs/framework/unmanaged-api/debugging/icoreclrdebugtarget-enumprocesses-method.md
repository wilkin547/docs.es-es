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
ms.openlocfilehash: 7e0219ae0d7d474812865f01e4e2fcfe2e4da991
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679369"
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
  
## <a name="parameters"></a>Parámetros  

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
  
## <a name="remarks"></a>Comentarios  

 Para liberar la memoria asignada por este método, llame al método [ICoreClrDebugTarget:: FreeMemory (](icoreclrdebugtarget-freememory-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteca:** mscordbi_macx86.dll  
  
 **.NET Framework versiones:** 3,5 SP1  
  
## <a name="see-also"></a>Consulte también

- [ICoreClrDebugTarget (Interfaz)](icoreclrdebugtarget-interface.md)
