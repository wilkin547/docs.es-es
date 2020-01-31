---
title: ICorDebugCode2::GetCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
ms.openlocfilehash: 4ad1fb1bcb43dda9796b54cbf868f89c001995da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777900"
---
# <a name="icordebugcode2getcompilerflags-method"></a>ICorDebugCode2::GetCompilerFlags (Método)

Obtiene las marcas que especifican las condiciones bajo las que este objeto de código se compiló Just-In-Time (JIT) o se generó usando el generador de imágenes nativas (Ngen.exe).

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a>Parameters

`pdwFlags`  
enuncia Un puntero a un valor de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) que especifica el comportamiento del compilador JIT o del generador de imágenes nativas.

## <a name="requirements"></a>Requisitos de

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
