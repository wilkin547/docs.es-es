---
description: 'Más información sobre: IGCHost:: collect (método)'
title: IGCHost::Collect (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
ms.openlocfilehash: b4c249e07709dc443ae7dd6c6a5bfd206b7f1caa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709703"
---
# <a name="igchostcollect-method"></a>IGCHost::Collect (Método)

Obliga a que se produzca una colección para la generación dada, independientemente del estado de la recolección de elementos no utilizados actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `Generation`  
 de Generación en la que se va a realizar la recolección de elementos no utilizados. Un valor de-1 indica que todas las generaciones se someterán a una recolección de elementos no utilizados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IGCHost (Interfaz)](igchost-interface.md)
