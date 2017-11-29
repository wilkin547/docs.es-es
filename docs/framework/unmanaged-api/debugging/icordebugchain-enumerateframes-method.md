---
title: "ICorDebugChain::EnumerateFrames (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.EnumerateFrames
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 87e2fbc0a4ca9d97ac7e57234383ebd8cee56211
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchainenumerateframes-method"></a>ICorDebugChain::EnumerateFrames (Método)
Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, comenzando por el marco más reciente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppFrames`  
 [out] Un puntero a la dirección de un objeto ICorDebugFrameEnum que es el enumerador de los marcos de pila.  
  
## <a name="remarks"></a>Comentarios  
 La cadena representa la pila de llamadas física del subproceso.  
  
 El `EnumerateFrames` método debe llamarse solo para cadenas administrados. La API de depuración no proporciona métodos para obtener los marcos incluidos en cadenas no administradas. El depurador debe utilizar otros medios para obtener esta información.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
