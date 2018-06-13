---
title: AssemblyFlags (Enumeración)
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fc6d08e960b0ba82c76945a318ec723546f71b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444911"
---
# <a name="assemblyflags-enumeration"></a>AssemblyFlags (Enumeración)
Contiene valores que describen las características de tiempo de ejecución de un ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`afImplicitExportedTypes`|Especifica que las definiciones de tipo exportado son implícitas dentro de los archivos que componen el ensamblado. En las versiones 1.0 y 1.1 de .NET Framework, se supone que este valor se establezca.|  
|`afImplicitResources`|Especifica que las definiciones de recursos están implícitas dentro de los archivos que componen el ensamblado. En .NET Framework 1.0 y 1.1, este valor siempre se supone que para puede establecer.|  
|`afNonSideBySideAppDomain`|Especifica que el ensamblado no puede ejecutarse con otras versiones si se están ejecutando en el mismo dominio de aplicación.|  
|`afNonSideBySideProcess`|Especifica que el ensamblado no puede ejecutarse con otras versiones si se están ejecutando en el mismo proceso.|  
|`afNonSideBySideMachine`|Especifica que el ensamblado no puede ejecutarse con otras versiones si se ejecutan en el mismo equipo.|  
  
## <a name="remarks"></a>Comentarios  
 Los valores entre 0 x 0010 y 0 x 0070, ambos inclusive, se utilizan para describir las características de compatibilidad en paralelo del ensamblado que se hace referencia. Si se establece ninguno de estos valores, se supone que el ensamblado es compatible en paralelo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MsCorEE.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
