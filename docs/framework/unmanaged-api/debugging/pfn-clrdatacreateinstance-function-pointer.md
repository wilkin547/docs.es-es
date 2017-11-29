---
title: "puntero a la función PFN_CLRDataCreateInstance"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PFN_CLRDataCreateInstance
api_location: mscordbi.dll
api_type: COM
f1_keywords: PFN_CLRDataCreateInstance
helpviewer_keywords: PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7ec5783381c667d666c447b6d9861d9baaad3907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a>puntero a la función PFN_CLRDataCreateInstance
Señala a una función que crea un objeto de interfaz para el elemento de destino especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `iid`  
 [in] El identificador de la interfaz que se creará una instancia.  
  
 `target`  
 [in] Un puntero a un usuario implementa [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) objeto que representa el elemento de destino para el que se va a crear el objeto de interfaz.  
  
 `iface`  
 [out] Un puntero a la dirección del objeto de interfaz devuelto.  
  
## <a name="remarks"></a>Comentarios  
 La `ICLRDataTarget` objeto se implementa el escritor de la aplicación de depuración. La implementación depende del tipo de elemento de destino que se va a representar. El elemento de destino puede ser un proceso, volcado de memoria, equipo remoto y así sucesivamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** ClrData.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones estáticas globales para la depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
