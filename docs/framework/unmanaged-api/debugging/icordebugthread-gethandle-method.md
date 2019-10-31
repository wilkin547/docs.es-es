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
ms.openlocfilehash: 33219d9a67379244e23da49c13617a4c4a2fa66d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133466"
---
# <a name="icordebugthreadgethandle-method"></a>ICorDebugThread::GetHandle (Método)
Obtiene el identificador actual para la parte activa de esta ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `phThreadHandle`  
 enuncia Un puntero a un HTHREAD que es el identificador de la parte activa de este subproceso.  
  
## <a name="remarks"></a>Comentarios  
 El identificador puede cambiar a medida que se ejecuta el proceso y puede ser diferente para distintas partes del subproceso.  
  
 Este identificador es propiedad de la API de depuración. El depurador debe duplicarlo antes de usarlo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
