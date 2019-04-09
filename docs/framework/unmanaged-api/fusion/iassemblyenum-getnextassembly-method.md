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
ms.openlocfilehash: 9a77e468363b59e76e55aa24d97d064189ad297e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117755"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="4d205-102">IAssemblyEnum::GetNextAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="4d205-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="4d205-103">Obtiene un puntero a la siguiente [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) incluidos en este [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="4d205-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d205-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d205-104">Syntax</span></span>  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d205-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d205-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="4d205-106">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="4d205-106">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="4d205-107">debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="4d205-107">must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="4d205-108">[out] El valor devuelto `IAssemblyName` puntero.</span><span class="sxs-lookup"><span data-stu-id="4d205-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="4d205-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="4d205-109">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="4d205-110">debe ser 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="4d205-110">must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d205-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d205-111">Requirements</span></span>  
 <span data-ttu-id="4d205-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d205-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d205-113">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4d205-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="4d205-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4d205-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d205-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d205-115">See also</span></span>

- [<span data-ttu-id="4d205-116">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d205-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="4d205-117">IAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d205-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
