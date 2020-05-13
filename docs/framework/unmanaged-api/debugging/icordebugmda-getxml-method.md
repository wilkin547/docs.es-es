---
title: ICorDebugMDA::GetXML (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
ms.openlocfilehash: 219aa27296dffa525bf3e2b836825437a8ce77b0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207654"
---
# <a name="icordebugmdagetxml-method"></a>ICorDebugMDA::GetXML (Método)
Obtiene la secuencia XML completa asociada al Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetXML (  
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
 enuncia Puntero a la longitud de la secuencia XML.  
  
 `szName`  
 enuncia Matriz en la que se va a almacenar la secuencia XML. La matriz puede estar vacía.  
  
## <a name="remarks"></a>Observaciones  
 El `GetXML` método puede afectar al rendimiento, dependiendo del tamaño de la secuencia XML asociada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugMDA (Interfaz)](icordebugmda-interface.md)
- [Diagnóstico de errores con asistentes de depuraciones administradas](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
