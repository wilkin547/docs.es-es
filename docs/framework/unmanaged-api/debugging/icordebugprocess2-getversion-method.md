---
description: 'Más información sobre: ICorDebugProcess2:: GetVersion (método)'
title: ICorDebugProcess2::GetVersion (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetVersion
helpviewer_keywords:
- GetVersion method, ICorDebugProcess2 interface [.NET Framework debugging]
- ICorDebugProcess2::GetVersion method [.NET Framework debugging]
ms.assetid: e11d5a75-61d9-4548-aedf-79c26079bd17
topic_type:
- apiref
ms.openlocfilehash: 8472e811ea4df1f99fb4e27b55f3561fae0c8a21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650110"
---
# <a name="icordebugprocess2getversion-method"></a>ICorDebugProcess2::GetVersion (Método)

Obtiene el número de versión del Common Language Runtime (CLR) que se ejecuta en este proceso.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a>Parámetros

`version`\
enuncia Puntero a una estructura de COR_VERSION que almacena el número de versión del motor en tiempo de ejecución.

## <a name="remarks"></a>Observaciones

El `GetVersion` método devuelve un código de error si no se ha cargado ningún tiempo de ejecución en el proceso.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
