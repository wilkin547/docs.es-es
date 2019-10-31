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
ms.openlocfilehash: 09c6431ec885c8b797dc9bb5f5c3ffe21890ccc7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107939"
---
# <a name="ienumdefinitionidentity-interface"></a>IEnumDefinitionIdentity (Interfaz)
Actúa como enumerador para una colección de objetos `IDefinitionIdentity`.  
  
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
  
|Método|Descripción|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|Obtiene un puntero de interfaz a un nuevo objeto `IEnumDefinitionIdentity` que contiene los mismos miembros que este `IEnumDefinitionIdentity`.|  
|`IEnumDefinitionIdentity::Next`|Obtiene el número especificado de objetos `IDefinitionIdentity`, comenzando en la posición actual.|  
|`IEnumDefinitionIdentity::Reset`|Mueve el puntero de instrucción al principio de este `IEnumDefinitionIdentity`.|  
|`IEnumDefinitionIdentity::Skip`|Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IDefinitionIdentity (interfaz)](idefinitionidentity-interface.md)
