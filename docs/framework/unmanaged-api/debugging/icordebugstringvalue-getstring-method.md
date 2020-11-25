---
title: ICorDebugStringValue::GetString (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
ms.openlocfilehash: 9051fa612bef3fbd817ff7bdadbd52c96ade5b7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697108"
---
# <a name="icordebugstringvaluegetstring-method"></a>ICorDebugStringValue::GetString (Método)

Obtiene la cadena a la que hace referencia este ICorDebugStringValue.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cchString`  
 [in] Tamaño de la matriz `szString`.  
  
 `pcchString`  
 enuncia Puntero al número de caracteres devueltos en la `szString` matriz.  
  
 `szString`  
 enuncia Matriz que almacena la cadena recuperada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
