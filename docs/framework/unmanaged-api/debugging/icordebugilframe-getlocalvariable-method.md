---
title: ICorDebugILFrame::GetLocalVariable (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
ms.openlocfilehash: 85f06b49aab1f1d1745bd7e359ed311c2ba1e44d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130978"
---
# <a name="icordebugilframegetlocalvariable-method"></a>ICorDebugILFrame::GetLocalVariable (Método)
Obtiene el valor de la variable local especificada en este marco de pila del lenguaje intermedio de Microsoft (MSIL).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwIndex`  
 de Índice de la variable local en este marco de pila de MSIL.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.  
  
## <a name="remarks"></a>Comentarios  
 El método `GetLocalVariable` se puede utilizar en un marco de pila de MSIL o en un marco compilado Just-in-Time (JIT).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
