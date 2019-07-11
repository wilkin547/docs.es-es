---
title: ICorDebugThread::GetHandle (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54981be7104eb04ac6347ad13b61a69f40d4377c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770622"
---
# <a name="icordebugthreadgethandle-method"></a>ICorDebugThread::GetHandle (Método)
Obtiene el identificador actual para la parte activa de este ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `phThreadHandle`  
 [out] Un puntero a HTHREAD que es el identificador de la parte activa de este subproceso.  
  
## <a name="remarks"></a>Comentarios  
 El identificador puede cambiar cuando se ejecuta el proceso y puede ser diferente para las distintas partes del subproceso.  
  
 Este identificador pertenece a la API de depuración. El depurador debe duplicarlo antes de usarlo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
