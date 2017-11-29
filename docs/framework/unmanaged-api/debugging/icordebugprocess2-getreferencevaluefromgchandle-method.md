---
title: "ICorDebugProcess2::GetReferenceValueFromGCHandle (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d40d1799a7c1572e8213fda3a163fb9a84060f92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>ICorDebugProcess2::GetReferenceValueFromGCHandle (Método)
Obtiene un puntero de referencia al objeto administrado especificado que tiene una colección de elementos no utilizados controlar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `handle`  
 [in] Un puntero a un objeto administrado que tiene un identificador de la colección de elementos no utilizados. Este valor es un <xref:System.IntPtr> objeto y se pueden recuperar desde el <xref:System.Runtime.InteropServices.GCHandle> para el objeto administrado.  
  
 `pOutValue`  
 [out] Un puntero a la dirección de un objeto ICorDebugReferenceValue que representa una referencia al objeto administrado especificado.  
  
## <a name="remarks"></a>Comentarios  
 No confunda el valor de referencia devuelto con un valor de referencia de la colección de elementos no utilizados.  
  
 La referencia devuelta se comporta como una referencia normal. Se deshabilita cuando la ejecución del código continúa después de un punto de interrupción. La duración del objeto de destino no se ve afectada por la duración del valor de referencia.  
  
> [!NOTE]
>  El `GetReferenceValueFromGCHandle` método no valida el identificador. Por lo tanto, la `GetReferenceValueFromGCHandle` método puede dañar potencialmente el depurador y el código que se está depurando si se pasa un identificador no válido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
