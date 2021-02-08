---
description: 'Más información acerca de: interfaz IEnumDefinitionIdentity ('
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
ms.openlocfilehash: 1055031c064115410334bbe4b20b48deee7ec4c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800167"
---
# <a name="ienumdefinitionidentity-interface"></a>IEnumDefinitionIdentity (Interfaz)

Actúa como enumerador para una colección de `IDefinitionIdentity` objetos.  
  
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
|`IEnumDefinitionIdentity::Clone`|Obtiene un puntero de interfaz a un nuevo `IEnumDefinitionIdentity` objeto que contiene los mismos miembros que este `IEnumDefinitionIdentity` .|  
|`IEnumDefinitionIdentity::Next`|Obtiene el número especificado de `IDefinitionIdentity` objetos, empezando en la posición actual.|  
|`IEnumDefinitionIdentity::Reset`|Mueve el puntero de instrucción al principio de este `IEnumDefinitionIdentity` .|  
|`IEnumDefinitionIdentity::Skip`|Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Isolation. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de Fusion](fusion-interfaces.md)
- [IDefinitionIdentity (Interfaz)](idefinitionidentity-interface.md)
