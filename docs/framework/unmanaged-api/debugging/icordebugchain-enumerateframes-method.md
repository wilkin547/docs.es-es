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
ms.openlocfilehash: ae6d81e6fdab0f8e3346d8a08a3b5ebc329a542a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730154"
---
# <a name="icordebugchainenumerateframes-method"></a>ICorDebugChain::EnumerateFrames (Método)

Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el fotograma más reciente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppFrames`  
 enuncia Puntero a la dirección de un objeto ICorDebugFrameEnum (que es el enumerador de los marcos de pila.  
  
## <a name="remarks"></a>Comentarios  

 La cadena representa la pila de llamadas física del subproceso.  
  
 `EnumerateFrames`Solo se debe llamar al método para las cadenas administradas. La API de depuración no proporciona métodos para obtener fotogramas contenidos en cadenas no administradas. El depurador debe utilizar otros medios para obtener esta información.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
