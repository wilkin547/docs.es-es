---
title: ICorDebugFunction::GetNativeCode (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: 5bb41b2b49922475550997f18832b391522e2f26
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137869"
---
# <a name="icordebugfunctiongetnativecode-method"></a>ICorDebugFunction::GetNativeCode (Método)
Obtiene el código nativo para la función representada por esta instancia de ICorDebugFunction.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppCode`  
 enuncia Un puntero a la instancia de ICorDebugCode que representa el código nativo de esta función, o null, si esta función es código del lenguaje intermedio de Microsoft (MSIL) que no se ha compilado Just-in-Time (JIT).  
  
## <a name="remarks"></a>Comentarios  
 Si la función representada por esta instancia de `ICorDebugFunction` se ha compilado JIT más de una vez, como en el caso de los tipos genéricos, `GetNativeCode` devuelve un objeto de código nativo aleatorio.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
