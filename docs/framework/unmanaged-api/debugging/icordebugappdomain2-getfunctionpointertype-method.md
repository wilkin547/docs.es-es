---
title: ICorDebugAppDomain2::GetFunctionPointerType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
ms.openlocfilehash: 5a6e0b009674ff52595aaa0ae4a060f1cdfd1398
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089046"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a>ICorDebugAppDomain2::GetFunctionPointerType (Método)
Obtiene un puntero a una función que tiene una firma especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `nTypeArgs`  
 de El número de argumentos de tipo para la función.  
  
 `ppTypeArgs`  
 de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de tipo de la función. El primer elemento es el tipo de valor devuelto; cada uno de los demás elementos es un tipo de parámetro.  
  
 `ppType`  
 enuncia Puntero a la dirección de un objeto `ICorDebugType` que representa el puntero a la función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
