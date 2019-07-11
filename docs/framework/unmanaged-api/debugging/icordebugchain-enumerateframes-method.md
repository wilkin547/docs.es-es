---
title: ICorDebugChain::EnumerateFrames (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc647805fcb7d8354a2540ac9424dc7155853444
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745037"
---
# <a name="icordebugchainenumerateframes-method"></a>ICorDebugChain::EnumerateFrames (Método)
Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el marco más reciente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppFrames`  
 [out] Un puntero a la dirección de un objeto ICorDebugFrameEnum que es el enumerador para los marcos de pila.  
  
## <a name="remarks"></a>Comentarios  
 La cadena representa la pila de llamadas física del subproceso.  
  
 El `EnumerateFrames` método debe llamarse únicamente para las cadenas administradas. La API de depuración no proporciona métodos para obtener fotogramas incluidos en cadenas no administradas. El depurador debe usar otros medios para obtener esta información.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
