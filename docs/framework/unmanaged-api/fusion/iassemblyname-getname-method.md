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
ms.openlocfilehash: 88a46ecadaf2b191e8321c5629bc77b0c67dfd3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697373"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="988b3-102">IAssemblyName::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="988b3-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="988b3-103">Obtiene el nombre sencillo y sin cifrar del ensamblado que hace referencia esta [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="988b3-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="988b3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="988b3-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="988b3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="988b3-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="988b3-106">[in, out] El tamaño de `pwzName` en caracteres anchos, incluido el carácter del terminador nulo.</span><span class="sxs-lookup"><span data-stu-id="988b3-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="988b3-107">[out] Un búfer para almacenar el nombre del ensamblado que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="988b3-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="988b3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="988b3-108">Requirements</span></span>  
 <span data-ttu-id="988b3-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="988b3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="988b3-110">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="988b3-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="988b3-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="988b3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="988b3-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="988b3-112">See also</span></span>

- [<span data-ttu-id="988b3-113">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="988b3-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
