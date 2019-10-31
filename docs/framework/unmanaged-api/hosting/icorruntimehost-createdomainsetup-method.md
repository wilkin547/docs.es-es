---
title: ICorRuntimeHost::CreateDomainSetup (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: 217874e625604613e67170a118a7bc3616e02c4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139649"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a>ICorRuntimeHost::CreateDomainSetup (Método)
Obtiene un puntero de interfaz de tipo IAppDomainSetup a una instancia de <xref:System.AppDomainSetup?displayProperty=nameWithType>. `IAppDomainSetup` proporciona métodos para configurar aspectos de un dominio de aplicación antes de que se cree.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pAppDomainSetup`  
 enuncia Puntero de interfaz a una instancia de <xref:System.AppDomainSetup?displayProperty=nameWithType>. Este parámetro se escribe como `IUnknown`, por lo que los llamadores generalmente deben llamar a `QueryInterface` en este puntero para obtener un puntero de interfaz de tipo `IAppDomainSetup`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La operación se realizó correctamente.|  
|S_FALSE|No se pudo completar la operación.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso. Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 Normalmente, el puntero devuelto por este método se pasa como un parámetro al método [createdomainex (](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versión de .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vea también

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
