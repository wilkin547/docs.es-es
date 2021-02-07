---
description: 'Más información sobre: ICorDebugFrame:: GetStackRange ((método)'
title: ICorDebugFrame::GetStackRange (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
ms.openlocfilehash: 1f1278e0c00addc3c14f4e1c8d3ed5aad0381526
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692906"
---
# <a name="icordebugframegetstackrange-method"></a>ICorDebugFrame::GetStackRange (Método)

Obtiene el intervalo de direcciones absolutas de este marco de pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pStart`  
 enuncia Puntero a `CORDB_ADDRESS` que especifica la dirección de inicio del marco de pila representado por este `ICorDebugFrame` objeto.  
  
 `pEnd`  
 enuncia Puntero a `CORDB_ADDRESS` que especifica la dirección final del marco de pila representado por este `ICorDebugFrame` objeto.  
  
## <a name="remarks"></a>Observaciones  

 El intervalo de direcciones de la pila es útil para juntar juntos los seguimientos de la pila intercalados recopilados de varios motores de depuración. El intervalo numérico no proporciona información sobre el contenido del marco de pila. Solo es significativo para la comparación de las ubicaciones de los marcos de pila.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
