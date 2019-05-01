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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07f3be81431201a4bb6011ea9b8f973061d3d101
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948880"
---
# <a name="icordebugprocess2getversion-method"></a>ICorDebugProcess2::GetVersion (Método)

Obtiene el número de versión de common language runtime (CLR) que se está ejecutando en este proceso.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetVersion (
    [out] COR_VERSION     *version
);
```

## <a name="parameters"></a>Parámetros

`version`\
[out] Un puntero a un COR_VERSION (estructura) que almacena el número de versión del tiempo de ejecución.

## <a name="remarks"></a>Comentarios

El `GetVersion` método devuelve un código de error si no se ha cargado ningún tiempo de ejecución en el proceso.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
