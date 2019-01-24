---
title: puntero a la función PFN_CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46e039aeec352c215046bebfb17e6fbd803962a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597494"
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a>puntero a la función PFN_CLRDataCreateInstance
Señala una función que crea un objeto de interfaz para el elemento de destino especificado.  
  
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
 [in] El identificador de la interfaz de creación de instancias.  
  
 `target`  
 [in] Un puntero a un usuario implementa [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) objeto que representa el elemento de destino para el que se va a crear el objeto de interfaz.  
  
 `iface`  
 [out] Un puntero a la dirección del objeto de interfaz devuelto.  
  
## <a name="remarks"></a>Comentarios  
 La `ICLRDataTarget` objeto es implementado por el sistema de escritura de la aplicación de depuración. La implementación depende del tipo de elemento de destino que se va a representar. El elemento de destino puede ser un proceso, volcado de memoria, equipo remoto y así sucesivamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: ClrData.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Funciones estáticas globales de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
