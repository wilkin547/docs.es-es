---
title: ASM_NAME (Enumeración)
ms.date: 03/30/2017
api_name:
- ASM_NAME
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_NAME
helpviewer_keywords:
- ASM_NAME enumeration [.NET Framework fusion]
ms.assetid: c8b65b19-d777-428f-bc0c-0d84c78a37bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b37e9c2874448b5fff82f6a37f6ca850875f2b04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112520"
---
# <a name="asmname-enumeration"></a>ASM_NAME (Enumeración)
Indica la versión, compilación, referencia cultural, firma etc., del ensamblado cuyas propiedades se recuperarán o establecidas por [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) métodos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
  
    ASM_NAME_PUBLIC_KEY = 0,  
    ASM_NAME_PUBLIC_KEY_TOKEN,  
    ASM_NAME_HASH_VALUE,  
    ASM_NAME_NAME,  
    ASM_NAME_MAJOR_VERSION,  
    ASM_NAME_MINOR_VERSION,  
    ASM_NAME_BUILD_NUMBER,  
    ASM_NAME_REVISION_NUMBER,  
    ASM_NAME_CULTURE,  
    ASM_NAME_PROCESSOR_ID_ARRAY,  
    ASM_NAME_OSINFO_ARRAY,  
    ASM_NAME_HASH_ALGID,  
    ASM_NAME_ALIAS,  
    ASM_NAME_CODEBASE_URL,  
    ASM_NAME_CODEBASE_LASTMOD,  
    ASM_NAME_NULL_PUBLIC_KEY,  
    ASM_NAME_NULL_PUBLIC_KEY_TOKEN,  
    ASM_NAME_CUSTOM,  
    ASM_NAME_NULL_CUSTOM,   
    ASM_NAME_MVID,  
    ASM_NAME_FILE_MAJOR_VERSION,  
    ASM_NAME_FILE_MINOR_VERSION,  
    ASM_NAME_FILE_BUILD_NUMBER,  
    ASM_NAME_FILE_REVISION_NUMBER,  
    ASM_NAME_RETARGET,  
    ASM_NAME_SIGNATURE_BLOB,  
    ASM_NAME_CONFIG_MASK,  
    ASM_NAME_ARCHITECTURE,  
    ASM_NAME_MAX_PARAMS  
  
} ASM_NAME;  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyName (Interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Enumeraciones de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
