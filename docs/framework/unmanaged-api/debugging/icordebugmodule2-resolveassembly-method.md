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
ms.openlocfilehash: e64e39d10d20f63430ffe9d2c4df8643e286a677
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210045"
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
de `mdToken`Valor que hace referencia al ensamblado.

`ppAssembly`\
enuncia Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado.

## <a name="remarks"></a>Observaciones

Si aún no se ha cargado el ensamblado cuando `ResolveAssembly` se llama a, se devuelve un valor HRESULT de CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
