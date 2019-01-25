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
ms.openlocfilehash: 324d8ce19f202cb6e9d0e4378ca61cf2a956d70e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648776"
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="f196b-102">ICeeGen::GetMethodBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="f196b-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="f196b-103">Obtiene un búfer del tamaño adecuado para el método en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="f196b-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="f196b-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="f196b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f196b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f196b-105">Syntax</span></span>  
  
```  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f196b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f196b-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="f196b-107">[in] La dirección virtual relativa del método para que se va a devolver el búfer.</span><span class="sxs-lookup"><span data-stu-id="f196b-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="f196b-108">[out] Un puntero al búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="f196b-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f196b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f196b-109">Requirements</span></span>  
 <span data-ttu-id="f196b-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f196b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f196b-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f196b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f196b-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f196b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f196b-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f196b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f196b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f196b-114">See also</span></span>
- [<span data-ttu-id="f196b-115">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f196b-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
