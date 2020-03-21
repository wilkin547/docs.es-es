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
ms.openlocfilehash: c7a1bf3cb10cbc8cdae2788b45e1badaf66a9dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178881"
---
# <a name="icordebugheapvalue2createhandle-method"></a>ICorDebugHeapValue2::CreateHandle (Método)
Crea un identificador del tipo especificado para el valor de montón representado por este ICorDebugHeapValue2 objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `type`  
 [en] Valor de la enumeración CorDebugHandleType que especifica el tipo de identificador que se va a crear.  
  
 `ppHandle`  
 [fuera] Puntero a la dirección de un ICorDebugHandleValue objeto que representa el nuevo identificador de este valor de montón.  
  
## <a name="remarks"></a>Observaciones  
 El identificador se creará en el dominio de aplicación asociado al valor del montón y dejará de ser válido si el dominio de aplicación se descarga.  
  
 Varias llamadas a esta función para el mismo valor de montón crearán varios identificadores. Dado que los identificadores afectan al rendimiento del recolector de elementos no utilizados, el depurador debe limitarse a un número relativamente pequeño de identificadores (alrededor de 256) que están activos a la vez.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
