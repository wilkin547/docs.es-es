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
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="1c9f2-102">IAssemblyEnum::GetNextAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="1c9f2-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="1c9f2-103">Obtiene un puntero a la siguiente [IAssemblyName](iassemblyname-interface.md) incluida en este objeto [IAssemblyEnum](iassemblyenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1c9f2-103">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c9f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c9f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c9f2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c9f2-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="1c9f2-106">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="1c9f2-107">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="1c9f2-108">enuncia Puntero `IAssemblyName` devuelto.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="1c9f2-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="1c9f2-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="1c9f2-110">`dwFlags` debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="1c9f2-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c9f2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c9f2-111">Requirements</span></span>  
 <span data-ttu-id="1c9f2-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c9f2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c9f2-113">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="1c9f2-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="1c9f2-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c9f2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c9f2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c9f2-115">See also</span></span>

- [<span data-ttu-id="1c9f2-116">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c9f2-116">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="1c9f2-117">IAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c9f2-117">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
