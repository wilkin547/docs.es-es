---
description: 'Más información sobre: ICorDebugAppDomain2:: GetFunctionPointerType ((método)'
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
ms.openlocfilehash: 2b9e10295df40b8e7db82e489fe8a6d28214ff38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772398"
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
 enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa el puntero a la función.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
