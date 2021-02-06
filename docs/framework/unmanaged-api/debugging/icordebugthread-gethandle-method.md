---
description: 'Más información acerca de: ICorDebugThread:: GetHandle (método)'
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
ms.openlocfilehash: 378bb395e56f0fc287a480d67d2047e082d0796f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659106"
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
  
## <a name="remarks"></a>Observaciones  

 El identificador puede cambiar a medida que se ejecuta el proceso y puede ser diferente para distintas partes del subproceso.  
  
 Este identificador es propiedad de la API de depuración. El depurador debe duplicarlo antes de usarlo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
