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
ms.openlocfilehash: 278120c6e1bc87a061a3f81f71bdb7b89cd421be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726566"
---
# <a name="icordebugheapvalue2createhandle-method"></a>ICorDebugHeapValue2::CreateHandle (Método)

Crea un identificador del tipo especificado para el valor del montón representado por este objeto Icordebugheapvalue2 (.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `type`  
 de Valor de la enumeración CorDebugHandleType (que especifica el tipo de controlador que se va a crear.  
  
 `ppHandle`  
 enuncia Puntero a la dirección de un objeto ICorDebugHandleValue que representa el nuevo identificador para este valor de montón.  
  
## <a name="remarks"></a>Comentarios  

 El identificador se creará en el dominio de aplicación que está asociado con el valor del montón y dejará de ser válido si se descarga el dominio de aplicación.  
  
 Varias llamadas a esta función para el mismo valor de montón crearán varios identificadores. Dado que los identificadores afectan al rendimiento del recolector de elementos no utilizados, el depurador se debe limitar a un número relativamente pequeño de identificadores (aproximadamente 256) que están activos a la vez.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
