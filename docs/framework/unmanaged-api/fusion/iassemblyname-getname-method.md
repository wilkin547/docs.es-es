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
ms.openlocfilehash: fe0b465d0e15fadde48c2278aa367632bda3f9ef
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473841"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="f6555-102">IAssemblyName::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="f6555-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="f6555-103">Obtiene el nombre sencillo y sin cifrar del ensamblado que hace referencia esta [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="f6555-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6555-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6555-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6555-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6555-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="f6555-106">[in, out] El tamaño de `pwzName` en caracteres anchos, incluido el carácter del terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="f6555-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="f6555-107">[out] Un búfer para almacenar el nombre del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="f6555-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6555-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6555-108">Requirements</span></span>  
 <span data-ttu-id="f6555-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6555-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6555-110">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f6555-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f6555-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6555-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6555-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6555-112">See also</span></span>
- [<span data-ttu-id="f6555-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6555-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
