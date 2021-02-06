---
description: 'Más información sobre: interfaz ICLRPolicyManager'
title: ICLRPolicyManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 8823f1db8b15b327306ff3c592b46c94537f4331
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637394"
---
# <a name="iclrpolicymanager-interface"></a>ICLRPolicyManager (Interfaz)

Proporciona métodos que permiten al host especificar las acciones de directiva que deben realizarse en caso de que se produzcan errores y tiempos de espera.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md)|Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce el error especificado.|  
|[Método SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md)|Especifica la acción de la Directiva que el CLR debe realizar cuando se agota el tiempo de espera de la operación especificada.|  
|[Método SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md)|Especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación especificada.|  
|[Método SetTimeout](iclrpolicymanager-settimeout-method.md)|Establece un valor de tiempo de espera para la operación especificada.|  
|[Método SetTimeoutAndAction](iclrpolicymanager-settimeoutandaction-method.md)|Establece un valor de tiempo de espera para la operación especificada y especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación.|  
|[Método SetUnhandledExceptionPolicy](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|Especifica el comportamiento de CLR cuando se produce una excepción no controlada.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrFailure (Enumeración)](eclrfailure-enumeration.md)
- [EClrOperation (Enumeración)](eclroperation-enumeration.md)
- [EPolicyAction (Enumeración)](epolicyaction-enumeration.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
