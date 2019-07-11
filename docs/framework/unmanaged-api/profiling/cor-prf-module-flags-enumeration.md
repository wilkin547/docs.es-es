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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f94867db6908f0999604511d9782b6f5abfb5e77
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752046"
---
# <a name="corprfmoduleflags-enumeration"></a>COR_PRF_MODULE_FLAGS (Enumeración)
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
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|El módulo se cargó desde el disco.|  
|COR_PRF_MODULE_NGEN|El módulo fue generado por el generador de imágenes nativas (Ngen.exe).|  
|COR_PRF_MODULE_DYNAMIC|El módulo fue creado por métodos en el <xref:System.Reflection.Emit?displayProperty=nameWithType> espacio de nombres.|  
|COR_PRF_MODULE_COLLECTIBLE|El recolector de elementos no utilizados administra la duración del módulo.|  
|COR_PRF_MODULE_RESOURCE|El módulo no contiene metadatos y se utiliza estrictamente como un recurso. Es el equivalente administrado de este bit la <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> método.|  
|COR_PRF_MODULE_FLAT_LAYOUT|No tiene formato, el diseño del módulo en la memoria no asignada. Si un módulo se este bit establecido, los generadores de perfiles que leer la información directamente desde el encabezado del archivo portable ejecutable (PE) tendrá que tener cuidado al interpretar direcciones virtuales relativas (RVA) en el encabezado.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|El indicador de tipo de contenido en tiempo de ejecución de Windows se establece en los metadatos de ensamblado de este módulo. Este es el caso de todos los módulos de los metadatos de Windows (.winmd).|  
  
## <a name="remarks"></a>Comentarios  
 Los bits de COR_PRF_MODULE_FLAGS se devuelven al generador de perfiles en el `pdwModuleFlags` parámetro de salida de la [ICorProfilerInfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) método. Algunas combinaciones de dos o más marcadores son posibles, pero no todas las combinaciones son posibles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
