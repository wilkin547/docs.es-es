---
title: ASSEMBLY_INFO (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ASSEMBLY_INFO
api_location: fusion.dll
api_type: COM
f1_keywords: ASSEMBLY_INFO
helpviewer_keywords: ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 215d80c3d207c2f50cfbd74386915b0467692b57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyinfo-structure"></a>ASSEMBLY_INFO (Estructura)
Contiene información sobre un ensamblado que está registrado en la caché global de ensamblados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`cbAssemblyInfo`|El tamaño, en bytes, de la estructura. Este campo está reservado para extensibilidad futura.|  
|`dwAssemblyFlags`|Marcadores que indican los detalles sobre el ensamblado de la instalación. Se admiten los siguientes valores:<br /><br /> -El valor ASSEMBLYINFO_FLAG_INSTALLED, que indica que el ensamblado está instalado. La versión actual de .NET Framework siempre establece `dwAssemblyFlags` en este valor.<br />-El valor ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, que indica que el ensamblado es un residente de carga. La versión actual de .NET Framework nunca establece `dwAssemblyFlags` en este valor.|  
|`uliAssemblySizeInKB`|El tamaño total, en kilobytes, de los archivos que contiene el ensamblado.|  
|`pszCurrentAssemblyPathBuf`|Un puntero a un búfer de cadena que contiene la ruta de acceso actual al archivo de manifiesto. La ruta de acceso debe terminar con un carácter nulo.|  
|`cchBuf`|El número de caracteres anchos, incluido el terminador nulo, que `pszCurrentAssemblyPathBuf` contiene.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [Caché global de ensamblados](../../../../docs/framework/app-domains/gac.md)
