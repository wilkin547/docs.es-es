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
ms.openlocfilehash: 7b1fc70380fff3c551c56043f49c2deda507e366
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703843"
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
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [EApiCategories (Enumeración)](eapicategories-enumeration.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
