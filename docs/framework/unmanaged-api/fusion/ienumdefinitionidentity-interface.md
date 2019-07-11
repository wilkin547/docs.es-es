---
title: IEnumDefinitionIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IEnumDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumDefinitionIdentity
helpviewer_keywords:
- IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bbd8476b7778de6d0023f3a8522a44be6626884
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751526"
---
# <a name="ienumdefinitionidentity-interface"></a>IEnumDefinitionIdentity (Interfaz)
Actúa como el enumerador para una colección de `IDefinitionIdentity` objetos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|Obtiene un puntero de interfaz a una nueva `IEnumDefinitionIdentity` objeto que contiene los mismos miembros que esto `IEnumDefinitionIdentity`.|  
|`IEnumDefinitionIdentity::Next`|Obtiene el número especificado de `IDefinitionIdentity` objetos, empezando en la posición actual.|  
|`IEnumDefinitionIdentity::Reset`|Mueve el puntero de instrucción al principio de este `IEnumDefinitionIdentity`.|  
|`IEnumDefinitionIdentity::Skip`|Mueve el puntero de instrucción al día por el número especificado de elementos, empezando por la posición actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Isolation.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IDefinitionIdentity (interfaz)](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
