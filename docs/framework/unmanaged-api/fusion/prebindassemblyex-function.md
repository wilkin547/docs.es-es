---
title: "PreBindAssemblyEx (Función)"
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
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 05977db8e01d00af6e160cb2993867cf83eb24c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="prebindassemblyex-function"></a>PreBindAssemblyEx (Función)
Obtiene el nombre para mostrar tras aplicar la directiva de un ensamblado.  
  
 Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pAppCtx`  
 [in] Identifica el contexto de la aplicación.  
  
 `pName`  
 [in] Identifica el nombre del ensamblado.  
  
 `pAsmParent`  
 [in] Identifica el ensamblado primario. Este parámetro se ignora.  
  
 `pwzRuntimeVersion`  
 [in] Identifica la versión en tiempo de ejecución.  
  
 `ppNamePostPolicy`  
 [out] Contiene el nombre para mostrar tras aplicar la directiva.  
  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved`debe ser una referencia nula.  
  
## <a name="remarks"></a>Comentarios  
 El `ppNamePostPolicy` parámetro de salida se establece únicamente si la función devuelve HRESULT FUSION_E_REF_DEF_MISMATCH. En caso contrario, es null.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
