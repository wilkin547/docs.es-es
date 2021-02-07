---
description: 'Más información sobre: ICorRuntimeHost:: Getdefaultdomain ((método)'
title: ICorRuntimeHost::GetDefaultDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
ms.openlocfilehash: 53be5e3db7bec396743edc728942ad54efc0ec16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753827"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a>ICorRuntimeHost::GetDefaultDomain (Método)

Obtiene un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> que representa el dominio predeterminado para el proceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pAppDomain`  
 enuncia Puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> a la <xref:System.AppDomain> instancia de que representa el dominio de aplicación predeterminado para el proceso.  
  
 Este puntero tiene tipo `IUnknown` , por lo que los llamadores generalmente deben llamar `QueryInterface` a para obtener un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La operación se realizó correctamente.|  
|S_FALSE|No se pudo completar la operación.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso. Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:** 1,0, 1,1  
  
## <a name="see-also"></a>Vea también

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [ICorRuntimeHost (Interfaz)](icorruntimehost-interface.md)
