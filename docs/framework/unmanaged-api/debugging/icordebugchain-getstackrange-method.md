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
ms.openlocfilehash: 226f8c431b90d53366aa5e504101e7de581ec570
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402475"
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
  
#### <a name="parameters"></a>Parámetros  
 `pStart`  
 [out] Un puntero a un `CORDB_ADDRESS` valor que es la dirección inicial del segmento de pila.  
  
 `pEnd`  
 [out] Un puntero a un `CORDB_ADDRESS` valor que es la dirección final del segmento de pila.  
  
## <a name="remarks"></a>Comentarios  
 El intervalo numérico es significativo únicamente para la comparación de ubicaciones de marco de pila. No se puede hacer ninguna suposición sobre lo que realmente se almacena en la pila.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
