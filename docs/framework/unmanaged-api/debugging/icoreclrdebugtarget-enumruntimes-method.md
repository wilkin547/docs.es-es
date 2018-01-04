---
title: "ICoreClrDebugTarget::EnumRuntimes (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget.EnumRuntimes
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a242d95785cf4421d30f716ac2987e42681aaef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a>ICoreClrDebugTarget::EnumRuntimes (Método)
Enumera los Common Language Runtime(CLR) del proceso especificado que se están ejecutando en un equipo remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwInternalProcessID`  
 [in] Identificador de proceso interno del proceso para el que desea enumerar los tiempos de ejecución. Se trata de `m_dwInternalID` desde correspondiente [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).  
  
 `pcRuntimes`  
 [out] Número de tiempos de ejecución que se devuelve en `ppRuntimes`. Este valor puede ser 0 (cero).  
  
 `ppRuntimes`  
 [out] Una matriz de [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) estructuras que representan los tiempos de ejecución cargan en el proceso de destino remoto.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 Correcto.  
  
 S_FALSE  
 `dwInternalProcessID` no coincide con ningún proceso que se esté ejecutando en el equipo, probablemente porque finalizó el proceso. `pcRuntimes` y `ppRuntimes` serán nulos.  
  
 E_OUTOFMEMORY  
 No se puede asignar memoria suficiente para `ppRuntimes`.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 Otros errores.  
  
## <a name="remarks"></a>Comentarios  
 Para liberar la memoria asignada por este método, llame a la [Icoreclrdebugtarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Biblioteca:** mscordbi_macx86.dll  
  
 **Versiones de .NET framework:** 3.5 SP1  
  
## <a name="see-also"></a>Vea también  
 [ICoreClrDebugTarget (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
