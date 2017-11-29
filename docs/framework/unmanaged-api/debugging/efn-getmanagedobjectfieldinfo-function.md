---
title: "_EFN_GetManagedObjectFieldInfo (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedObjectFieldInfo
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedObjectFieldInfo
helpviewer_keywords: _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3df09c9107b683381f21891a1001140c493a024
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedobjectfieldinfo-function"></a>_EFN_GetManagedObjectFieldInfo (Función)
Obtiene el desplazamiento desde el inicio de un objeto hasta un campo y el valor del campo, a partir del puntero de objeto y nombre de campo especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `Client`  
 [in] Un puntero al cliente de depuración.  
  
 `objAddr`  
 [in] Un puntero de objeto administrado.  
  
 szFieldName  
 [in] Un puntero de objeto administrado por el nombre de campo.  
  
 `pValue`  
 [out] El valor del campo. Este parámetro puede ser NULL.  
  
 `pOffset`  
 [out] El desplazamiento de `objAddr` al campo. Este parámetro puede ser NULL.  
  
## <a name="remarks"></a>Comentarios  
 Si el desplazamiento es 0, no se escribe ningún desplazamiento.  
  
 Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor 0xa0 y el código de error de 0 x 1000.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** SOS_Stacktrace.h  
  
 **Versión de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones estáticas globales para la depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
