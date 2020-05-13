---
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
ms.openlocfilehash: 391b848d3b3f66f6af6bf3adbefb6e94d526e748
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213509"
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
