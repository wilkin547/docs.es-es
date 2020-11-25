---
title: ICLRHostProtectionManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
ms.openlocfilehash: e8ead998907d55b0bfbf82e5f6f4e7c504f657ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714164"
---
# <a name="iclrhostprotectionmanager-interface"></a>ICLRHostProtectionManager (Interfaz)

Permite al host bloquear la ejecución de clases, métodos, propiedades y campos administrados específicos en código de confianza parcial.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[SetEagerSerializeGrantSets](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|Proporciona una garantía de que no se producirán nunca ciertas condiciones de carrera poco frecuentes que pueden provocar errores graves de Common Language Runtime (CLR).|  
|[Método SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md)|Especifica las categorías de tipos administrados y miembros que se deben bloquear para que no se ejecuten en código de confianza parcial.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [EApiCategories (Enumeración)](eapicategories-enumeration.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
