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
ms.openlocfilehash: e1e114070f39e75254fc1bc0f8c1bf3e4733d5a2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703375"
---
# <a name="iclrprobingassemblyenum-interface"></a>ICLRProbingAssemblyEnum (Interfaz)
Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante la información de identidad del ensamblado que es interna del Common Language Runtime (CLR), sin necesidad de crear o comprender esa identidad.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Get (Método)](iclrprobingassemblyenum-get-method.md)|Obtiene la identidad del ensamblado en el índice especificado.|  
  
## <a name="remarks"></a>Observaciones  
 Los métodos como [ICLRAssemblyIdentityManager:: getprobingassembliesfromreference (](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) devuelven una `ICLRProbingAssemblyEnum` instancia de.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [ICLRAssemblyIdentityManager (Interfaz)](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList (Interfaz)](iclrassemblyreferencelist-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
