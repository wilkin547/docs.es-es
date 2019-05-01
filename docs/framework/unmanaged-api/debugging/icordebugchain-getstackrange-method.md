---
title: ICorDebugChain::GetStackRange (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac40927ac9469e4a2fb74fb550287130b9bb9f83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989461"
---
# <a name="icordebugchaingetstackrange-method"></a>ICorDebugChain::GetStackRange (Método)
Obtiene el intervalo de direcciones del segmento de pila para esta cadena.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pStart`  
 [out] Un puntero a un `CORDB_ADDRESS` valor que es la dirección inicial del segmento de pila.  
  
 `pEnd`  
 [out] Un puntero a un `CORDB_ADDRESS` valor que es la dirección final del segmento de pila.  
  
## <a name="remarks"></a>Comentarios  
 El intervalo numérico es significativo únicamente para la comparación de las ubicaciones del marco de pila. No se puede hacer ninguna suposición sobre lo que realmente se almacena en la pila.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
