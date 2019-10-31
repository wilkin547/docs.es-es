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
ms.openlocfilehash: ade404557d65fa073b6a0e66fe8234b41223ecde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134436"
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
 [in] Reservado para extensibilidad futura. `pvReserved` debe ser una referencia nula.  
  
 `ppName`  
 enuncia Puntero `IAssemblyName` devuelto.  
  
 `dwFlags`  
 [in] Reservado para extensibilidad futura. `dwFlags` debe ser 0 (cero).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyName (interfaz)](iassemblyname-interface.md)
- [IAssemblyEnum (interfaz)](iassemblyenum-interface.md)
