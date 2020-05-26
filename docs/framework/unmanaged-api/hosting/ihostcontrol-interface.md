---
title: IHostControl (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl
helpviewer_keywords:
- IHostControl interface [.NET Framework hosting]
ms.assetid: a4ae0d1f-ade9-4b0a-a122-93ed11a5e6b3
topic_type:
- apiref
ms.openlocfilehash: 9dd89abb332853b966aa81dc506099b7af6ca3b2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804932"
---
# <a name="ihostcontrol-interface"></a>IHostControl (Interfaz)
Proporciona métodos para configurar la carga de ensamblados y para determinar qué interfaces de hospedaje admite el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetHostManager](ihostcontrol-gethostmanager-method.md)|Obtiene un puntero de interfaz a la implementación del host de la interfaz con el especificado `IID` .|  
|[Método SetAppDomainManager](ihostcontrol-setappdomainmanager-method.md)|Notifica al host que se ha creado un dominio de aplicación.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.AppDomainManager>
- [ICLRRuntimeHost (Interfaz)](iclrruntimehost-interface.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
