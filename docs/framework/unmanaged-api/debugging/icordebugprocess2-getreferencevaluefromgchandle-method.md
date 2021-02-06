---
description: 'Más información sobre: ICorDebugProcess2:: Getreferencevaluefromgchandle ((método)'
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
ms.openlocfilehash: 02047dee9116d34a365242f2a532766eb60e1c81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650246"
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
 de Un puntero a un objeto administrado que tiene un identificador de recolección de elementos no utilizados. Este valor es un <xref:System.IntPtr> objeto y se puede recuperar de <xref:System.Runtime.InteropServices.GCHandle> para el objeto administrado.  
  
 `pOutValue`  
 enuncia Puntero a la dirección de un objeto ICorDebugReferenceValue que representa una referencia al objeto administrado especificado.  
  
## <a name="remarks"></a>Observaciones  

 No confunda el valor de referencia devuelto con un valor de referencia de recolección de elementos no utilizados.  
  
 La referencia devuelta se comporta como una referencia normal. Está deshabilitada cuando la ejecución del código continúa después de un punto de interrupción. La duración del objeto de destino no se ve afectada por la duración del valor de referencia.  
  
> [!NOTE]
> El `GetReferenceValueFromGCHandle` método no valida el identificador. Por consiguiente, el `GetReferenceValueFromGCHandle` método puede dañar potencialmente el depurador y el código que se está depurando si se pasa un identificador no válido.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
