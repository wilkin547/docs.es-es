---
description: 'Más información acerca de: Clrdatacreateinstance ((función)'
title: CLRDataCreateInstance (Función)
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- DLLExport
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
ms.openlocfilehash: 923b0c687d2b337eacb475973927452e3b47ad0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747262"
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
  
## <a name="remarks"></a>Observaciones  

 El `ICLRDataTarget` escritor de la aplicación de depuración implementa el objeto. La implementación depende del tipo de elemento de destino que se está representando. El elemento de destino puede ser un proceso, un volcado de memoria, una máquina remota, etc.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** ClrData. idl  
  
 **Biblioteca:** CorGuids.lib  

 **Ensamblado**: mscordacwks.dll, mscordbi.dll
  
 **.NET Framework versiones:** Disponible desde .NET Framework 2,0
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para la depuración](debugging-global-static-functions.md)
