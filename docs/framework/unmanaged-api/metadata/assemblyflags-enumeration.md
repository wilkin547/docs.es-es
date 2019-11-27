---
title: AssemblyFlags (enumeración)
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: ffb5953c843a338b4548253457a0c3b1ca0c20f5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444300"
---
# <a name="assemblyflags-enumeration"></a>AssemblyFlags (enumeración)
Contiene valores que describen las características de tiempo de ejecución de un ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`afImplicitExportedTypes`|Especifica que las definiciones de tipos exportadas están implícitas dentro de los archivos que componen el ensamblado. En las versiones 1,0 y 1,1 de .NET Framework, se supone que este valor siempre está establecido.|  
|`afImplicitResources`|Especifica que las definiciones de recursos están implícitas dentro de los archivos que componen el ensamblado. En el .NET Framework 1,0 y 1,1, siempre se supone que se establece este valor.|  
|`afNonSideBySideAppDomain`|Especifica que el ensamblado no se puede ejecutar con otras versiones si se ejecutan en el mismo dominio de aplicación.|  
|`afNonSideBySideProcess`|Especifica que el ensamblado no se puede ejecutar con otras versiones si se ejecutan en el mismo proceso.|  
|`afNonSideBySideMachine`|Especifica que el ensamblado no se puede ejecutar con otras versiones si se ejecutan en el mismo equipo.|  
  
## <a name="remarks"></a>Comentarios  
 Los valores entre 0x0010 y 0x0070, ambos incluidos, se usan para describir las características de compatibilidad en paralelo del ensamblado al que se hace referencia. Si no se establece ninguno de estos valores, se supone que el ensamblado es compatible en paralelo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MsCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
