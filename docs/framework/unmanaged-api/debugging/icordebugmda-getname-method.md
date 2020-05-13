---
title: ICorDebugMDA::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
ms.openlocfilehash: 6a6769265a2e140f1fa001bb8240bc5d4bd76018
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213678"
---
# <a name="icordebugmdagetname-method"></a>ICorDebugMDA::GetName (Método)
Obtiene una cadena que contiene el nombre del Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cchName`  
 [in] Tamaño de la matriz `szName`.  
  
 `pcchName`  
 enuncia Puntero a la longitud del nombre.  
  
 `szName`  
 enuncia Matriz en la que se va a almacenar el nombre.  
  
## <a name="remarks"></a>Observaciones  
 Los nombres de MDA son valores únicos. El `GetName` método es una alternativa de rendimiento adecuada para obtener la secuencia XML y extraer el nombre de la secuencia basada en el esquema.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugMDA (Interfaz)](icordebugmda-interface.md)
- [Diagnóstico de errores con asistentes de depuraciones administradas](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
