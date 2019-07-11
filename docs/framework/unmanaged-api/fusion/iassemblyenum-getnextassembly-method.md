---
title: IAssemblyEnum::GetNextAssembly (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d64096ea693be41359aef63c04674ca77769c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760979"
---
# <a name="iassemblyenumgetnextassembly-method"></a>IAssemblyEnum::GetNextAssembly (Método)
Obtiene un puntero a la siguiente [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) incluidos en este [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pvReserved`  
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
 `ppName`  
 [out] El valor devuelto `IAssemblyName` puntero.  
  
 `dwFlags`  
 [in] Reservado para extensibilidad futura. `dwFlags` debe ser 0 (cero).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyName (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [IAssemblyEnum (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
