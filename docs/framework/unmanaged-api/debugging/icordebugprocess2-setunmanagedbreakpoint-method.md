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
ms.openlocfilehash: 1a883878107569145b97d5793f0628efefb13545
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675248"
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
 de `CORDB_ADDRESS` Objeto que especifica el desplazamiento de la imagen nativa.  
  
 `bufsize`  
 de Tamaño, en bytes, de la `buffer` matriz.  
  
 `buffer`  
 enuncia Una matriz que contiene el código de operación reemplazado por el punto de interrupción.  
  
 `bufLen`  
 enuncia Puntero al número de bytes devuelto en la `buffer` matriz.  
  
## <a name="remarks"></a>Comentarios  

 Si el desplazamiento de la imagen nativa se encuentra dentro del Common Language Runtime (CLR), se omitirá el punto de interrupción. Esto permite al CLR evitar el envío de un punto de interrupción fuera de banda, cuando el depurador establece el punto de interrupción.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
