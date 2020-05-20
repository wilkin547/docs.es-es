---
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
ms.openlocfilehash: 8645878132359b6218cd62b1ff707208de53704b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442155"
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
 El depurador llama al `InitializeForProcess` método en el momento de la creación para inicializar la presentación del enlace. `InitializeForProcess`se debe llamar a en el momento de la creación antes de llamar a cualquier otro método en `IBindingDisplay` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** BindingDisplay. h  
  
 **Biblioteca:** BindingDisplay. idl  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [IBindingDisplay (Interfaz)](ibindingdisplay-interface.md)
