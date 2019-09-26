---
title: CLRDataCreateInstance (Función)
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5d44f9b5dc42147959d3f1d127a64d39258f515
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274264"
---
# <a name="clrdatacreateinstance-function"></a>CLRDataCreateInstance (Función)
Crea un objeto de interfaz para el elemento de destino especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CLRDataCreateInstance (  
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
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: ClrData.idl  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales de depuración](debugging-global-static-functions.md)
