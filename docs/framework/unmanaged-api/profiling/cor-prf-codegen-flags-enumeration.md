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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 321318b63368ed6e57d235cf97d94485352f8686
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211366"
---
# <a name="corprfcodegenflags-enumeration"></a>COR_PRF_CODEGEN_FLAGS (Enumeración)
Define las marcas de generación de código que se pueden establecer con el [Icorprofilerfunctioncontrol](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    COR_PRF_CODEGEN_DISABLE_INLINING =          0x0001,  
    COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS = 0x0002,  
} COR_PRF_CODEGEN_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_CODEGEN_DISABLE_INLINING`|No hay ninguna función insertarse en el cuerpo de la función. Sin embargo, la función en sí se puede insertar en sus llamadores.|  
|`COR_PRF_CODEGEN_DISABLE_ALL_OPTIMIZATIONS`|Todas las optimizaciones se deshabilitará para el cuerpo de la función. Sin embargo, la propia función puede seguir siendo insertada en sus llamadores.|  
  
## <a name="remarks"></a>Comentarios  
 El `COR_PRF_CODEGEN_FLAGS` enumeración la utiliza el [Icorprofilerfunctioncontrol](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) método para habilitar el generador de perfiles controlar la generación de código para la función recompilada con JIT.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
