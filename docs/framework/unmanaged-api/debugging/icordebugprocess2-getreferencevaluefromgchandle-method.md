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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f38f9a3ebd88e0a5abb7a6bc8cb4026dc7d0f068
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736936"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle (Método)
Obtiene un puntero de referencia al objeto administrado especificado que tiene una colección de elementos no utilizados de identificador.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `handle`  
 [in] Un puntero a un objeto administrado que tiene un identificador de la colección de elementos no utilizados. Este valor es un <xref:System.IntPtr> objeto y se pueden recuperar desde el <xref:System.Runtime.InteropServices.GCHandle> para el objeto administrado.  
  
 `pOutValue`  
 [out] Un puntero a la dirección de un objeto ICorDebugReferenceValue que representa una referencia al objeto administrado especificado.  
  
## <a name="remarks"></a>Comentarios  
 No confunda el valor devuelto de referencia con un valor de referencia de la colección de elementos no utilizados.  
  
 La referencia devuelta se comporta como una referencia normal. Se deshabilita cuando la ejecución del código continúa después de un punto de interrupción. La duración del objeto de destino no se ve afectada por la duración del valor de referencia.  
  
> [!NOTE]
>  El `GetReferenceValueFromGCHandle` método no valida el identificador. Por lo tanto, el `GetReferenceValueFromGCHandle` método puede dañar el depurador y el código que se está depurando si se pasa un identificador no válido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
