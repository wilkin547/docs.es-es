---
title: CreateAssemblyCache (Función)
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
ms.openlocfilehash: 5ef100680328e9ad6261bb9188d7509efa9ab479
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108865"
---
# <a name="createassemblycache-function"></a>CreateAssemblyCache (Función)
Obtiene un puntero a una nueva instancia de [IAssemblyCache](iassemblycache-interface.md) que representa la caché global de ensamblados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppAsmCache`  
 enuncia Puntero `IAssemblyCache` devuelto.  
  
 `dwReserved`  
 [in] Reservado para extensibilidad futura. `dwReserved` debe ser 0 (cero).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Fusion. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IAssemblyCache (interfaz)](iassemblycache-interface.md)
- [Funciones estáticas globales de la fusión](fusion-global-static-functions.md)
- [Caché global de ensamblados](../../app-domains/gac.md)
