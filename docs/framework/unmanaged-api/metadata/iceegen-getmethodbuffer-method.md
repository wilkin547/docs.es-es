---
title: ICeeGen::GetMethodBuffer (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c0aea6185095a30aae9197c875aa9b9ac581d406
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121542"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="0e0a1-102">ICeeGen::GetMethodBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="0e0a1-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="0e0a1-103">Obtiene un búfer del tamaño adecuado para el método en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="0e0a1-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="0e0a1-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="0e0a1-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e0a1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e0a1-105">Syntax</span></span>  
  
```  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e0a1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e0a1-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="0e0a1-107">[in] La dirección virtual relativa del método para que se va a devolver el búfer.</span><span class="sxs-lookup"><span data-stu-id="0e0a1-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="0e0a1-108">[out] Un puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="0e0a1-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e0a1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e0a1-109">Requirements</span></span>  
 <span data-ttu-id="0e0a1-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e0a1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e0a1-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="0e0a1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e0a1-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e0a1-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0e0a1-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0e0a1-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0e0a1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e0a1-114">See also</span></span>

- [<span data-ttu-id="0e0a1-115">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e0a1-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
