---
title: _EFN_GetManagedObjectFieldInfo (Función)
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfa4db00662ed3abffbfd01e6e36005cd272a271
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664595"
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
 [out] El desplazamiento desde `objAddr` al campo. Este parámetro puede ser NULL.  
  
## <a name="remarks"></a>Comentarios  
 Si el desplazamiento es 0, no se escribe ningún desplazamiento.  
  
 Si no hay ningún código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor 0xa0 y un código de error de 0 x 1000.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: SOS_Stacktrace.h  
  
 **Versión de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Funciones estáticas globales de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
