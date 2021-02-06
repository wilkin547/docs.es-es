---
description: 'Más información acerca de: _EFN_GetManagedObjectName función'
title: _EFN_GetManagedObjectName (Función)
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectName
helpviewer_keywords:
- _EFN_GetManagedObjectName function [.NET Framework debugging]
ms.assetid: 6e7c6bee-7ced-495f-bf6c-2a5f0c716f7e
topic_type:
- apiref
ms.openlocfilehash: 4fa47848ace973f43acbcf8ab0322db4b974b205
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637903"
---
# <a name="_efn_getmanagedobjectname-function"></a>\_EFN \_ GetManagedObjectName función)

Obtiene el nombre de un tipo mediante el puntero de objeto administrado proporcionado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT _EFN_GetManagedObjectName(  
    [in]  PDEBUG_CLIENT  Client,  
    [in]  ULONG64        objAddr,  
    [out] __out_ecount(cbName) PSTR szName,  
    [out] ULONG          cbName  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `Client`  
 de Puntero al cliente de depuración.  
  
 `objAddr`  
 de Puntero de objeto administrado.  
  
 szName  
 enuncia Nombre del tipo.  
  
 `cbName`  
 enuncia Número de caracteres disponibles en el búfer de cadena.  
  
## <a name="remarks"></a>Observaciones  

 Si no hay código administrado en el subproceso actualmente en contexto, la función devuelve HRESULT SOS_E_NOMANAGEDCODE con un valor de instalación de 0XA0 y un código de error de 0x1000.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** SOS_Stacktrace. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para la depuración](debugging-global-static-functions.md)
