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
ms.openlocfilehash: 366a48e5f6abd92f0c6f796f40bdd263181da4a8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213483"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)
Establece las marcas que se deben incrustar en una imagen precompilada para que el motor en tiempo de ejecución cargue esa imagen en el proceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pdwFlags`  
 de Un valor de la enumeración [cordebugjitcompilerflags (](cordebugjitcompilerflags-enumeration.md) que especifica las marcas de compilador que se usan para seleccionar la imagen precompilada correcta.  
  
## <a name="remarks"></a>Observaciones  
 El `SetDesiredNGENCompilerFlags` método especifica las marcas que se deben incrustar en una imagen precompilada para que el motor en tiempo de ejecución cargue esa imagen en este proceso. Las marcas establecidas por este método solo se usan para seleccionar la imagen precompilada correcta. Si no existe tal imagen, el motor en tiempo de ejecución cargará en su lugar la imagen de lenguaje intermedio de Microsoft (MSIL) y el compilador Just-in-Time (JIT). En ese caso, el depurador todavía debe usar el método [ICorDebugModule2:: setjitcompilerflags (](icordebugmodule2-setjitcompilerflags-method.md) para establecer las marcas como se desea para la compilación JIT.  
  
 Si se carga una imagen, pero debe realizarse alguna compilación JIT para esa imagen (que será el caso si la imagen contiene elementos genéricos), las marcas de compilador especificadas por el `SetDesiredNGENCompilerFlags` método se aplicarán a la compilación JIT adicional.  
  
 `SetDesiredNGENCompilerFlags`Se debe llamar al método durante la devolución de llamada [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) . `SetDesiredNGENCompilerFlags`Se producirá un error al intentar llamar al método después. Además, se producirá un error al intentar establecer marcas que no estén definidas en la `CorDebugJITCompilerFlags` enumeración o que no sean válidas para el proceso especificado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebug (Interfaz)](icordebug-interface.md)
- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
