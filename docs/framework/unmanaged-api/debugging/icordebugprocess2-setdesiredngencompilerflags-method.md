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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ba2b0cf7d88104eaadd434732edf3c1d4060e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422706"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>ICorDebugProcess2::SetDesiredNGENCompilerFlags (Método)
Establece las marcas que deben incrustarse en una imagen precompilada para el tiempo de ejecución cargar esa imagen en el proceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pdwFlags`  
 [in] Un valor de la [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeración que especifica las marcas de compilador se usa para seleccionar la imagen precompilada correcta.  
  
## <a name="remarks"></a>Comentarios  
 El `SetDesiredNGENCompilerFlags` método especifica las marcas que deben incrustarse en una imagen precompilada para que el tiempo de ejecución cargará esa imagen en este proceso. Las marcas establecidas por este método se usan solo para seleccionar la imagen precompilada correcta. Si no existe ninguna imagen de este tipo, el tiempo de ejecución cargará la imagen de lenguaje intermedio (MSIL) de Microsoft y el compilador de just-in-time (JIT) en su lugar. En ese caso, el depurador debe utilizar todavía el [ICorDebugModule2:: SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) método para establecer las marcas según sea necesario para la compilación JIT.  
  
 Si se carga una imagen, pero alguna compilación JIT debe realizarse para esa imagen (que será el caso si la imagen contiene genéricos), los marcadores del compilador especificados por el `SetDesiredNGENCompilerFlags` método se aplicará a la compilación JIT adicional.  
  
 El `SetDesiredNGENCompilerFlags` debe llamar al método durante la [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) devolución de llamada. Intenta llamar a la `SetDesiredNGENCompilerFlags` método posteriormente producirá un error. Además, si se intenta establecer marcas que no están definidas en el `CorDebugJITCompilerFlags` se producirá un error en la enumeración o son no válida para el proceso especificado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
