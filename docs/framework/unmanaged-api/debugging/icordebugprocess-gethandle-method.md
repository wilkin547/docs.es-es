---
title: ICorDebugProcess::GetHandle (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: e4061580d59b0cf2a6e6e481d5242005e9452caf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128874"
---
# <a name="icordebugprocessgethandle-method"></a>ICorDebugProcess::GetHandle (Método)
Obtiene un identificador para el proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a>Parámetros  
 `phProcessHandle`  
 enuncia Puntero a un `HPROCESS` que es el identificador del proceso.  
  
## <a name="remarks"></a>Comentarios  
 El identificador recuperado es propiedad de la interfaz de depuración. El depurador debe duplicar el identificador antes de usarlo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
