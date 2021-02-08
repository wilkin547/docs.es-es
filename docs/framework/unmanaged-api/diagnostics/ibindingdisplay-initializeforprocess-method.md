---
description: 'Más información sobre: IBindingDisplay:: InitializeForProcess ((método)'
title: IBindingDisplay::InitializeForProcess (Método)
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
ms.openlocfilehash: cf7f0f4d057659089bd7da173e5fac98a7c00dad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800417"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a>IBindingDisplay::InitializeForProcess (Método)

Inicializa el objeto [IBindingDisplay](ibindingdisplay-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pid`  
 de Identificador del proceso.  
  
## <a name="remarks"></a>Observaciones  

 El depurador llama al `InitializeForProcess` método en el momento de la creación para inicializar la presentación del enlace. `InitializeForProcess` se debe llamar a en el momento de la creación antes de llamar a cualquier otro método en `IBindingDisplay` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** BindingDisplay. h  
  
 **Biblioteca:** BindingDisplay. idl  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IBindingDisplay (Interfaz)](ibindingdisplay-interface.md)
