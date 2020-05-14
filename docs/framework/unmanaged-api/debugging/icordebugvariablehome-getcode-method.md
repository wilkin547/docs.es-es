---
title: 'ICorDebugVariableHome:: GetCode (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
ms.openlocfilehash: 87d611a7b6e12a9238b00131326e8205778769e6
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396591"
---
# <a name="icordebugvariablehomegetcode-method"></a>ICorDebugVariableHome:: GetCode (método)
Obtiene la instancia de "ICorDebugCode" que contiene este objeto [ICorDebugVariableHome](icordebugvariablehome-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppCode`  
 enuncia Puntero a la dirección de la instancia de "ICorDebugCode" que contiene este objeto [ICorDebugVariableHome](icordebugvariablehome-interface.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
