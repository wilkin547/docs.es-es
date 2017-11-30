---
title: "AssemblyFlags (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyFlags
helpviewer_keywords: AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 91760b6d16b663257bf3d89915da3bd88b3411bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
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
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [IMetaDataAssemblyEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
