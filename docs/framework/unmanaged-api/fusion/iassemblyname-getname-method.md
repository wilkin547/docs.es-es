---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e471ee99af57ef980850c0a5d3e4f5f2973967ac
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796605"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="b7d54-102">IAssemblyName::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="b7d54-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="b7d54-103">Obtiene el nombre simple y sin cifrar del ensamblado al que hace referencia este objeto de [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b7d54-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7d54-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7d54-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7d54-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7d54-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="b7d54-106">[in, out] Tamaño de `pwzName` en caracteres anchos, incluido el carácter de terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="b7d54-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="b7d54-107">enuncia Búfer que contiene el nombre del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b7d54-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7d54-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7d54-108">Requirements</span></span>  
 <span data-ttu-id="b7d54-109">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7d54-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d54-110">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b7d54-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b7d54-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7d54-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7d54-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7d54-112">See also</span></span>

- [<span data-ttu-id="b7d54-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7d54-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
