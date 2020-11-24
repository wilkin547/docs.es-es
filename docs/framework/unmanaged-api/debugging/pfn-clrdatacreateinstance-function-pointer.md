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
ms.openlocfilehash: 68a5b8bb1568f10699653479357b02b2e847cc02
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671972"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a>puntero a la función PFN_CLRDataCreateInstance

Apunta a una función que crea un objeto de interfaz para el elemento de destino especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `iid`  
 de Identificador de la interfaz de la que se va a crear una instancia.  
  
 `target`  
 de Un puntero a un objeto [ICLRDataTarget](iclrdatatarget-interface.md) implementado por el usuario que representa el elemento de destino para el que se va a crear el objeto de interfaz.  
  
 `iface`  
 enuncia Puntero a la dirección del objeto de interfaz devuelto.  
  
## <a name="remarks"></a>Comentarios  

 El `ICLRDataTarget` escritor de la aplicación de depuración implementa el objeto. La implementación depende del tipo de elemento de destino que se está representando. El elemento de destino puede ser un proceso, un volcado de memoria, una máquina remota, etc.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones estáticas globales para la depuración](debugging-global-static-functions.md)
