---
title: ICLRProbingAssemblyEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
ms.openlocfilehash: e1459c1604f3f8f043fd9b61533235ab7861c910
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120561"
---
# <a name="iclrprobingassemblyenum-interface"></a>ICLRProbingAssemblyEnum (Interfaz)
Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante la información de identidad del ensamblado que es interna del Common Language Runtime (CLR), sin necesidad de crear o comprender esa identidad.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Get (método)](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|Obtiene la identidad del ensamblado en el índice especificado.|  
  
## <a name="remarks"></a>Comentarios  
 Los métodos como [ICLRAssemblyIdentityManager:: getprobingassembliesfromreference (](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) devuelven una instancia de `ICLRProbingAssemblyEnum`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyIdentityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
