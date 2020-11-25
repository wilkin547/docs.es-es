---
title: ICorDebugILFrame::GetArgument (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
ms.openlocfilehash: d17179dbeb9564b16c0c95a43502a53a67d3b9b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703170"
---
# <a name="icordebugilframegetargument-method"></a>ICorDebugILFrame::GetArgument (Método)

Obtiene el valor del argumento especificado en este marco de pila del lenguaje intermedio de Microsoft (MSIL).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `dwIndex`  
 de Índice del argumento de este marco de pila de MSIL.  
  
 `ppValue`  
 [out] Puntero a la dirección de un objeto ICorDebugValue que representa el valor recuperado.  
  
## <a name="remarks"></a>Comentarios  

 El `GetArgument` método se puede utilizar en un marco de pila de MSIL o en un marco compilado Just-in-Time (JIT).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
