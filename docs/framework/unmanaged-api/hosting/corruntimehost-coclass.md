---
title: CorRuntimeHost (Coclase)
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 942c9544a6ce868c3b6296569d4a16a44281cdba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758322"
---
# <a name="corruntimehost-coclass"></a>CorRuntimeHost (Coclase)
Proporciona interfaces para administrar las aplicaciones que se ejecutan por common language runtime.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a>Interfaces  
  
|Interfaz|DESCRIPCIÓN|  
|---------------|-----------------|  
|[ICorConfiguration (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|Proporciona métodos para la configuración de common language runtime (CLR).|  
|[ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|Proporciona métodos que permiten al host iniciar y detener de forma explícita, common language runtime para crear y configurar dominios de aplicación, tener acceso al dominio de forma predeterminada y para enumerar todos los dominios que se ejecutan en el proceso.|  
|[IDebuggerInfo (interfaz)](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|Proporciona métodos para obtener información sobre el estado de los servicios de depuración.|  
|[IGCHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|Proporciona métodos para obtener información sobre el sistema de recopilación de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos.|  
|"IValidator"|Proporciona métodos para la validación de imágenes ejecutables portables y generar informes detallados de errores de validación.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.idl  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Coclases para el hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
