---
description: 'Más información acerca de: ICorRuntimeHost:: GetConfiguration (método)'
title: ICorRuntimeHost::GetConfiguration (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: d3e3f065c3957fb29daa11ed7c46858a53865c91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784839"
---
# <a name="icorruntimehostgetconfiguration-method"></a>ICorRuntimeHost::GetConfiguration (Método)

Obtiene un objeto que permite al host especificar la configuración de devolución de llamada del Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pConfiguration`  
 enuncia Puntero a la dirección de un objeto [ICorConfiguration](icorconfiguration-interface.md) que se puede usar para configurar el CLR.  
  
## <a name="remarks"></a>Observaciones  

 CLR se debe configurar antes de su inicialización; de lo contrario, el `GetConfiguration` método devuelve un valor HRESULT que indica un error.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:** 1,0, 1,1  
  
## <a name="see-also"></a>Vea también

- [ICorRuntimeHost (Interfaz)](icorruntimehost-interface.md)
