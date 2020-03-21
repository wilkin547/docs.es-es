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
ms.openlocfilehash: fb8b8f3e29c141e91587a4d0cdc81cdabccdbc9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178648"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>ICorDebugProcess2::SetUnmanagedBreakpoint (Método)
Establece un punto de interrupción no administrado en el desplazamiento de imagen nativo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `address`  
 [en] Objeto `CORDB_ADDRESS` que especifica el desplazamiento de imagen nativa.  
  
 `bufsize`  
 [en] El tamaño, en bytes, de la `buffer` matriz.  
  
 `buffer`  
 [fuera] Matriz que contiene el código de operación que se reemplaza por el punto de interrupción.  
  
 `bufLen`  
 [fuera] Puntero al número de bytes `buffer` devueltos en la matriz.  
  
## <a name="remarks"></a>Observaciones  
 Si el desplazamiento de imagen nativa está dentro de Common Language Runtime (CLR), se omitirá el punto de interrupción. Esto permite que CLR evite distribuir un punto de interrupción fuera de banda, cuando el depurador establece el punto de interrupción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
