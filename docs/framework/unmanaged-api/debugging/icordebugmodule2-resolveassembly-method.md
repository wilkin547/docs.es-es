---
description: 'Más información sobre: ICorDebugModule2:: Resolveassembly ((método)'
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
ms.openlocfilehash: fba53b8ff76e4d3deb1876d2a20a7a2edc20bd06
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722599"
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
de `mdToken` Valor que hace referencia al ensamblado.

`ppAssembly`\
enuncia Puntero a la dirección de un objeto ICorDebugAssembly que representa el ensamblado.

## <a name="remarks"></a>Observaciones

Si aún no se ha cargado el ensamblado cuando `ResolveAssembly` se llama a, se devuelve un valor HRESULT de CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
