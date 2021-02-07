---
description: 'Más información sobre: IAssemblyName:: GetName (método)'
title: IAssemblyName::GetName (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
ms.openlocfilehash: 04cd6258c2fc60c9fc40e1e4b731e5c04a8d3112
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760750"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="c9971-103">IAssemblyName::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="c9971-103">IAssemblyName::GetName Method</span></span>

<span data-ttu-id="c9971-104">Obtiene el nombre simple y sin cifrar del ensamblado al que hace referencia este objeto de [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c9971-104">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9971-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9971-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9971-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9971-106">Parameters</span></span>  

 `lpcwBuffer`  
 <span data-ttu-id="c9971-107">[in, out] Tamaño de `pwzName` en caracteres anchos, incluido el carácter de terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="c9971-107">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="c9971-108">enuncia Búfer que contiene el nombre del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="c9971-108">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9971-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9971-109">Requirements</span></span>  

 <span data-ttu-id="c9971-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9971-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9971-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c9971-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c9971-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9971-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9971-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9971-113">See also</span></span>

- [<span data-ttu-id="c9971-114">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9971-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
