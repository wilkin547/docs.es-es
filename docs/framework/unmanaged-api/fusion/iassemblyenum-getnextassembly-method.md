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
ms.openlocfilehash: 73c531378355100fdfca264ea9f96ff4d7c7ceda
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796677"
---
# <a name="iassemblyenumgetnextassembly-method"></a>IAssemblyEnum::GetNextAssembly (Método)
Obtiene un puntero a la siguiente [IAssemblyName](iassemblyname-interface.md) incluida en este objeto [IAssemblyEnum](iassemblyenum-interface.md) .  
  
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
 [in] Reservado para extensibilidad futura. `pvReserved`debe ser una referencia nula.  
  
 `ppName`  
 enuncia Puntero devuelto `IAssemblyName` .  
  
 `dwFlags`  
 [in] Reservado para extensibilidad futura. `dwFlags`debe ser 0 (cero).  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyName (interfaz)](iassemblyname-interface.md)
- [IAssemblyEnum (interfaz)](iassemblyenum-interface.md)
