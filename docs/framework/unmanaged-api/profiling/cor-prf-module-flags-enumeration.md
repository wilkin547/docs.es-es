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
ms.openlocfilehash: 48617022940d889abedb9a9d25f04782371c4a5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451950"
---
# <a name="corprfmoduleflags-enumeration"></a>COR_PRF_MODULE_FLAGS (Enumeración)
Especifica las propiedades de un módulo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|COR_PRF_MODULE_NGEN|El módulo se generó con el generador de imágenes nativas (Ngen.exe).|  
|COR_PRF_MODULE_DYNAMIC|El módulo fue creado con métodos de la <xref:System.Reflection.Emit?displayProperty=nameWithType> espacio de nombres.|  
|COR_PRF_MODULE_COLLECTIBLE|Duración del módulo administrado por el recolector de elementos no utilizados.|  
|COR_PRF_MODULE_RESOURCE|El módulo no contiene metadatos y se usa estrictamente como un recurso. Es el equivalente administrado de este bit la <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> método.|  
|COR_PRF_MODULE_FLAT_LAYOUT|El diseño del módulo en la memoria es plano, sin asignar. Si un módulo se este bit establecido, los generadores de perfiles que leer la información directamente desde el encabezado del archivo portable ejecutable (PE) tendrá que tener cuidado al interpretar direcciones virtuales relativas (RVA) en el encabezado.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|El indicador de tipo de contenido en tiempo de ejecución de Windows se establece en los metadatos de ensamblado de este módulo. Este es el caso de todos los módulos de metadatos de Windows (.winmd).|  
  
## <a name="remarks"></a>Comentarios  
 Los bits de COR_PRF_MODULE_FLAGS se devuelven al generador de perfiles en el `pdwModuleFlags` parámetro de salida de la [ICorProfilerInfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) método. Algunas combinaciones de dos o más marcas son posibles, pero no todas las combinaciones son posibles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
