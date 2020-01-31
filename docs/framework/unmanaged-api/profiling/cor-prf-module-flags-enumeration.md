---
title: COR_PRF_MODULE_FLAGS (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_MODULE_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MODULE_FLAGS
helpviewer_keywords:
- COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type:
- apiref
ms.openlocfilehash: 0f6fb469aa9d6d40b762bfd2feec28c28299732f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867118"
---
# <a name="cor_prf_module_flags-enumeration"></a>COR_PRF_MODULE_FLAGS (Enumeración)
Especifica las propiedades de un módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum  
{  
    COR_PRF_MODULE_DISK             = 0x00000001,  
    COR_PRF_MODULE_NGEN             = 0x00000002,  
    COR_PRF_MODULE_DYNAMIC          = 0x00000004,  
    COR_PRF_MODULE_COLLECTIBLE      = 0x00000008,  
    COR_PRF_MODULE_RESOURCE         = 0x00000010,  
    COR_PRF_MODULE_FLAT_LAYOUT      = 0x00000020,  
    COR_PRF_MODULE_WINDOWS_RUNTIME  = 0x00000040  
}   COR_PRF_MODULE_FLAGS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|El módulo se cargó desde el disco.|  
|COR_PRF_MODULE_NGEN|El generador de imágenes nativas (Ngen. exe) generó el módulo.|  
|COR_PRF_MODULE_DYNAMIC|Los métodos del espacio de nombres <xref:System.Reflection.Emit?displayProperty=nameWithType> crearon el módulo.|  
|COR_PRF_MODULE_COLLECTIBLE|El recolector de elementos no utilizados administra la duración del módulo.|  
|COR_PRF_MODULE_RESOURCE|El módulo no contiene metadatos y se usa estrictamente como un recurso. El equivalente administrado de este bit es el método <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType>.|  
|COR_PRF_MODULE_FLAT_LAYOUT|El diseño del módulo en memoria es plano, no asignado. Si un módulo tiene este bit establecido, los perfiles que leen la información directamente del encabezado del archivo portable ejecutable (PE) tendrán que tener cuidado al interpretar las direcciones virtuales relativas (RVA) en el encabezado.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|La marca de tipo de contenido Windows Runtime se establece en los metadatos del ensamblado de este módulo. Este es el caso de todos los módulos de metadatos de Windows (. winmd).|  
  
## <a name="remarks"></a>Notas  
 Los bits de COR_PRF_MODULE_FLAGS se devuelven al generador de perfiles en el parámetro de salida `pdwModuleFlags` del método [ICorProfilerInfo3:: GetModuleInfo2 (](icorprofilerinfo3-getmoduleinfo2-method.md) . Algunas combinaciones de dos o más marcas son posibles, pero no todas las combinaciones son posibles.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
