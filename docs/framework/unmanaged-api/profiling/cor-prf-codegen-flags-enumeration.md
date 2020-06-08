---
title: COR_PRF_CODEGEN_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_CODEGEN_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODEGEN_FLAGS
helpviewer_keywords:
- COR_PRF_CODEGEN_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 3e184022-0247-4824-a23d-6b29593d8d01
topic_type:
- apiref
ms.openlocfilehash: c2c7ae7a8930949c79b5e24e2da75f3b4649e7f6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500993"
---
# <a name="cor_prf_codegen_flags-enumeration"></a>COR_PRF_CODEGEN_FLAGS (Enumeración)
Define las marcas de generación de código que se pueden establecer con el método [ICorProfilerFunctionControl:: setcodegenflags (](icorprofilerfunctioncontrol-setcodegenflags-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|No se insertará ninguna función en el cuerpo de esta función. Sin embargo, la propia función puede estar insertada en sus llamadores.|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|Todas las optimizaciones se deshabilitarán para el cuerpo de esta función. Sin embargo, la propia función todavía puede estar insertada en sus llamadores.|  
  
## <a name="remarks"></a>Comentarios  
 El `COR_PRF_CODEGEN_FLAGS` método [ICorProfilerFunctionControl:: setcodegenflags (](icorprofilerfunctioncontrol-setcodegenflags-method.md) usa la enumeración para permitir que el generador de perfiles controle la generación de código para la función recompilada JIT.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
