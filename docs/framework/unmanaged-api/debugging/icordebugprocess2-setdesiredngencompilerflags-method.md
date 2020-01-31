---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
ms.openlocfilehash: 9f62d94d30c8c4f23073895b8ff0f7afa2dbad6b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792495"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)
Establece las marcas que se deben incrustar en una imagen precompilada para que el motor en tiempo de ejecución cargue esa imagen en el proceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pdwFlags`  
 de Un valor de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) que especifica las marcas de compilador que se usan para seleccionar la imagen precompilada correcta.  
  
## <a name="remarks"></a>Notas  
 El método `SetDesiredNGENCompilerFlags` especifica las marcas que se deben incrustar en una imagen precompilada para que el motor en tiempo de ejecución cargue esa imagen en este proceso. Las marcas establecidas por este método solo se usan para seleccionar la imagen precompilada correcta. Si no existe tal imagen, el motor en tiempo de ejecución cargará en su lugar la imagen de lenguaje intermedio de Microsoft (MSIL) y el compilador Just-in-Time (JIT). En ese caso, el depurador todavía debe usar el método [ICorDebugModule2:: setjitcompilerflags (](icordebugmodule2-setjitcompilerflags-method.md) para establecer las marcas como se desea para la compilación JIT.  
  
 Si se carga una imagen, pero debe realizarse alguna compilación JIT para esa imagen (que será el caso si la imagen contiene genéricos), las marcas de compilador especificadas por el método `SetDesiredNGENCompilerFlags` se aplicarán a la compilación JIT adicional.  
  
 Se debe llamar al método `SetDesiredNGENCompilerFlags` durante la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) . Después, se producirá un error al intentar llamar al método `SetDesiredNGENCompilerFlags`. Además, se producirá un error al intentar establecer marcas que no están definidas en la enumeración `CorDebugJITCompilerFlags` o que no son válidas para el proceso especificado.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](icordebug-interface.md)
- [ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)
