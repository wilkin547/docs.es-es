---
title: ICorDebugHeapValue2::CreateHandle (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5c5a12df5689f113857045ba4bcda696bda8f5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756717"
---
# <a name="icordebugheapvalue2createhandle-method"></a>ICorDebugHeapValue2::CreateHandle (Método)
Crea un identificador del tipo especificado para el valor de montón representado por este objeto ICorDebugHeapValue2.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `type`  
 [in] Un valor de la enumeración CorDebugHandleType que especifica el tipo de identificador que se va a crear.  
  
 `ppHandle`  
 [out] Un puntero a la dirección de un objeto ICorDebugHandleValue que representa el nuevo identificador para este valor de montón.  
  
## <a name="remarks"></a>Comentarios  
 El identificador se creará en el dominio de aplicación que está asociado con el valor de montón y dejará de ser válido si se descarga el dominio de aplicación.  
  
 Varias llamadas a esta función para el mismo valor de montón creará varios identificadores. Porque identificadores afectan al rendimiento del recolector de elementos no utilizados, el depurador debe limitar a un número relativamente pequeño de identificadores (aproximadamente 256) que están activos simultáneamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
