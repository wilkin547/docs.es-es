---
description: 'Más información acerca de: interfaz ICLRAssemblyIdentityManager'
title: ICLRAssemblyIdentityManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager
helpviewer_keywords:
- ICLRAssemblyIdentityManager interface [.NET Framework hosting]
ms.assetid: 6a81c6fe-cc22-4062-ae27-d6eeee03a7b9
topic_type:
- apiref
ms.openlocfilehash: d6238ec51a8cc1bb61eaa96e5297656c447df785
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790064"
---
# <a name="iclrassemblyidentitymanager-interface"></a>ICLRAssemblyIdentityManager (Interfaz)

Proporciona métodos que admiten la comunicación entre el host y el Common Language Runtime (CLR) acerca de los ensamblados.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetBindingIdentityFromFile](iclrassemblyidentitymanager-getbindingidentityfromfile-method.md)|Obtiene los datos de enlace de identidad del ensamblado en la ruta de acceso de archivo especificada.|  
|[Método GetBindingIdentityFromStream](iclrassemblyidentitymanager-getbindingidentityfromstream-method.md)|Obtiene los datos de identidad del ensamblado canónico para el ensamblado en la secuencia especificada.|  
|[Método GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md)|Obtiene una instancia de [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) de la lista proporcionada de identidades de ensamblado parciales.|  
|[Método GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md)|Obtiene un enumerador [ICLRProbingAssemblyEnum](iclrprobingassemblyenum-interface.md) para las identidades de ensamblado a las que hace referencia el ensamblado con la identidad especificada.|  
|[Método GetReferencedAssembliesFromFile](iclrassemblyidentitymanager-getreferencedassembliesfromfile-method.md)|Obtiene una instancia de [ICLRReferenceAssemblyEnum](iclrreferenceassemblyenum-interface.md) que contiene una lista de ensamblados a los que hace referencia el ensamblado en la ruta de acceso de archivo especificada.|  
|[Método GetReferencedAssembliesFromStream](iclrassemblyidentitymanager-getreferencedassembliesfromstream-method.md)|Obtiene un puntero a un `ICLRReferenceAssemblyEnum` objeto que contiene datos de identidad de ensamblado para los ensamblados a los que hace referencia el ensamblado en la secuencia especificada.|  
|[Método IsStronglyNamed](iclrassemblyidentitymanager-isstronglynamed-method.md)|Obtiene un valor que indica si el ensamblado especificado tiene un nombre seguro.|  
  
## <a name="remarks"></a>Observaciones  

 Utilice `ICLRAssemblyIdentityManager` para obtener instancias de `ICLRAssemblyReferenceList` y para enumerar las identidades de ensamblado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyReferenceList (Interfaz)](iclrassemblyreferencelist-interface.md)
- [ICLRProbingAssemblyEnum (Interfaz)](iclrprobingassemblyenum-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
