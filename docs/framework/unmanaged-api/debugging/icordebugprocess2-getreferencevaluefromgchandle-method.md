---
title: ICorDebugProcess2::GetReferenceValueFromGCHandle (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
ms.openlocfilehash: 47647bf0460507b4c88b47bf87bfcc3bf620aecc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137218"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle (Método)
Obtiene un puntero de referencia al objeto administrado especificado que tiene un identificador de recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `handle`  
 de Un puntero a un objeto administrado que tiene un identificador de recolección de elementos no utilizados. Este valor es un objeto de <xref:System.IntPtr> y se puede recuperar del <xref:System.Runtime.InteropServices.GCHandle> para el objeto administrado.  
  
 `pOutValue`  
 enuncia Puntero a la dirección de un objeto ICorDebugReferenceValue que representa una referencia al objeto administrado especificado.  
  
## <a name="remarks"></a>Comentarios  
 No confunda el valor de referencia devuelto con un valor de referencia de recolección de elementos no utilizados.  
  
 La referencia devuelta se comporta como una referencia normal. Está deshabilitada cuando la ejecución del código continúa después de un punto de interrupción. La duración del objeto de destino no se ve afectada por la duración del valor de referencia.  
  
> [!NOTE]
> El método `GetReferenceValueFromGCHandle` no valida el identificador. Por lo tanto, el método `GetReferenceValueFromGCHandle` podría dañar el depurador y el código que se está depurando si se pasa un identificador no válido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
