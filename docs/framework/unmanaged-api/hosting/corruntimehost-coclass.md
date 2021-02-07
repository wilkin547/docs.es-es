---
description: 'Más información acerca de: coclase Corruntimehost ('
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
ms.openlocfilehash: cd2d01075e5c8264337e1e989b3d9fdc6bf68962
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760647"
---
# <a name="corruntimehost-coclass"></a>CorRuntimeHost (Coclase)

Proporciona interfaces para administrar las aplicaciones que se ejecutan en el Common Language Runtime.  
  
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
  
|Interfaz|Descripción|  
|---------------|-----------------|  
|[ICorConfiguration (Interfaz)](icorconfiguration-interface.md)|Proporciona métodos para configurar el Common Language Runtime (CLR).|  
|[ICorRuntimeHost (Interfaz)](icorruntimehost-interface.md)|Proporciona métodos que permiten al host iniciar y detener el Common Language Runtime explícitamente, para crear y configurar dominios de aplicación, para tener acceso al dominio predeterminado y para enumerar todos los dominios que se ejecutan en el proceso.|  
|[IDebuggerInfo (Interfaz)](idebuggerinfo-interface.md)|Proporciona métodos para obtener información sobre el estado de los servicios de depuración.|  
|[IGCHost (Interfaz)](igchost-interface.md)|Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.|  
|IValidator|Proporciona métodos para la validación de imágenes ejecutables portables e informes detallados de errores de validación.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. idl  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Coclases para el hospedaje](hosting-coclasses.md)
