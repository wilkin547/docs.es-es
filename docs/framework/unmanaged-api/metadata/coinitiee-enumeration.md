---
title: "COINITIEE (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ad117c3efd31cc176281e571b7fde11229c097e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="coinitiee-enumeration"></a>COINITIEE (Enumeración)
Especifica las constantes utilizadas por [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) al inicializar common language runtime.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|Modo de inicialización predeterminado. Esto inicializa el tiempo de ejecución y crea el valor predeterminado <xref:System.AppDomain>.|  
|`COINITEE_DLL`|Se inicializa para ejecutar un archivo DLL administrado.|  
|`COINITEE_MAIN`|Se inicializa para ejecutar un archivo ejecutable administrado. Esto inicializa el tiempo de ejecución pero no crea el valor predeterminado <xref:System.AppDomain>, que se crea después de escribir la rutina principal del archivo EXE.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
