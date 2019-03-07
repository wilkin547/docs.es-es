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
ms.openlocfilehash: b5e86461973d24e9bd61df9ce27da5a614a49aa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471022"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="8c19e-102">ICeeGen::AllocateMethodBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="8c19e-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="8c19e-103">Crea un búfer del tamaño especificado para un método y obtiene la dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="8c19e-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="8c19e-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="8c19e-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c19e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c19e-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c19e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8c19e-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="8c19e-107">[in] La longitud del búfer que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="8c19e-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="8c19e-108">[out] El búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="8c19e-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="8c19e-109">[out] La dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="8c19e-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c19e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c19e-110">Requirements</span></span>  
 <span data-ttu-id="8c19e-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c19e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c19e-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="8c19e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c19e-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8c19e-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c19e-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c19e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c19e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c19e-115">See also</span></span>
- [<span data-ttu-id="8c19e-116">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8c19e-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
