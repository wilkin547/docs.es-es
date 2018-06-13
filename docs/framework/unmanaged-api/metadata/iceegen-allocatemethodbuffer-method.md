---
title: ICeeGen::AllocateMethodBuffer (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f56376d4400f4e24aefe2d1e5d4ad504b1d281cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446009"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="40fbe-102">ICeeGen::AllocateMethodBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="40fbe-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="40fbe-103">Crea un búfer del tamaño especificado para un método y obtiene la dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="40fbe-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="40fbe-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="40fbe-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40fbe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40fbe-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40fbe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40fbe-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="40fbe-107">[in] La longitud del búfer que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="40fbe-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="40fbe-108">[out] El búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="40fbe-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="40fbe-109">[out] La dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="40fbe-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40fbe-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40fbe-110">Requirements</span></span>  
 <span data-ttu-id="40fbe-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40fbe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40fbe-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="40fbe-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="40fbe-113">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40fbe-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="40fbe-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40fbe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40fbe-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="40fbe-115">See Also</span></span>  
 [<span data-ttu-id="40fbe-116">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40fbe-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
