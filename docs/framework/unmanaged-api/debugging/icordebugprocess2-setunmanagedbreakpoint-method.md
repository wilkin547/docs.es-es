---
title: ICorDebugProcess2::SetUnmanagedBreakpoint (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4326c6d8a3ee780cf63652badc8c527f55a075c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>ICorDebugProcess2::SetUnmanagedBreakpoint (Método)
Establece un punto de interrupción no administrado en el desplazamiento de imagen nativa especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]   
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `address`  
 [in] Un `CORDB_ADDRESS` objeto que especifica el desplazamiento de imagen nativa.  
  
 `bufsize`  
 [in] El tamaño, en bytes, de la `buffer` matriz.  
  
 `buffer`  
 [out] Una matriz que contiene el código de operación que se ha reemplazado por el punto de interrupción.  
  
 `bufLen`  
 [out] Un puntero al número de bytes devueltos en el `buffer` matriz.  
  
## <a name="remarks"></a>Comentarios  
 Si el desplazamiento de imagen nativa está dentro de common language runtime (CLR), el punto de interrupción se omitirá. Esto permite que el CLR evitar enviar un punto de interrupción fuera de banda, cuando el punto de interrupción se establece mediante el depurador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
