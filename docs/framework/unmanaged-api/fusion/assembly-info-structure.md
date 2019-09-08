---
title: ASSEMBLY_INFO (Estructura)
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 390ab4881396bbc01337d087f05b6066153bfed1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795487"
---
# <a name="assembly_info-structure"></a>ASSEMBLY_INFO (Estructura)
Contiene información acerca de un ensamblado registrado en la caché global de ensamblados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`cbAssemblyInfo`|Tamaño de la estructura, en bytes. Este campo está reservado para extensibilidad futura.|  
|`dwAssemblyFlags`|Marcas que indican los detalles de la instalación del ensamblado. Se admiten los siguientes valores:<br /><br /> : El valor de ASSEMBLYINFO_FLAG_INSTALLED, que indica que el ensamblado está instalado. La versión actual de .NET Framework siempre establece `dwAssemblyFlags` en este valor.<br />: El valor de ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, que indica que el ensamblado es un residente de carga. La versión actual de la .NET Framework nunca establece `dwAssemblyFlags` en este valor.|  
|`uliAssemblySizeInKB`|Tamaño total, en kilobytes, de los archivos que contiene el ensamblado.|  
|`pszCurrentAssemblyPathBuf`|Un puntero a un búfer de cadena que contiene la ruta de acceso actual al archivo de manifiesto. La ruta de acceso debe terminar con un carácter nulo.|  
|`cchBuf`|El número de caracteres anchos, incluido el terminador null `pszCurrentAssemblyPathBuf` , que contiene.|  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de fusión](fusion-structures.md)
- [Caché global de ensamblados](../../app-domains/gac.md)
