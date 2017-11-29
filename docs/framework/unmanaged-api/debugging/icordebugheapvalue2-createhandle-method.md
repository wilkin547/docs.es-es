---
title: "ICorDebugHeapValue2::CreateHandle (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue2.CreateHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7feef9af174a63976729f91b5a0b4967fea55b23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapvalue2createhandle-method"></a>ICorDebugHeapValue2::CreateHandle (Método)
Crea un identificador del tipo especificado para el valor de montón representado por este objeto ICorDebugHeapValue2.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `type`  
 [in] Un valor de la enumeración CorDebugHandleType que especifica el tipo de identificador que se va a crear.  
  
 `ppHandle`  
 [out] Un puntero a la dirección de un objeto ICorDebugHandleValue que representa el nuevo identificador para este valor de montón.  
  
## <a name="remarks"></a>Comentarios  
 El identificador se crea en el dominio de aplicación que está asociado con el valor de montón y ya no serán válido si se descarga el dominio de aplicación.  
  
 Varias llamadas a esta función para el mismo valor de montón crearán varios identificadores. Porque identificadores afectan al rendimiento del recolector de elementos no utilizados, el depurador debe limitar a un número relativamente pequeño de identificadores (aproximadamente 256) que están activos simultáneamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
