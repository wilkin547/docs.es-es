---
title: ICorDebugModule2::ResolveAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd899422287d34407778f67e5b4dfd2f33ffd00c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994830"
---
# <a name="icordebugmodule2resolveassembly-method"></a>ICorDebugModule2::ResolveAssembly (Método)

Resuelve el ensamblado al que hace referencia el token de metadatos especificado.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT ResolveAssembly (
    [in]  mdToken             tkAssemblyRef,
    [out] ICorDebugAssembly   **ppAssembly
);
```

## <a name="parameters"></a>Parámetros

`tkAssemblyRef`\
[in] Un `mdToken` valor al que hace referencia al ensamblado.

`ppAssembly`\
[out] Un puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado.

## <a name="remarks"></a>Comentarios

Si el ensamblado no se ha cargado cuando `ResolveAssembly` se denomina un HRESULT se devuelve el valor CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
