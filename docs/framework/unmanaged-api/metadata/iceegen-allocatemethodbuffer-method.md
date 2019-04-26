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
ms.openlocfilehash: 7be1bd2934fbb2e09a39c3042fa9ae314e89d629
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905611"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="c50e8-102">ICeeGen::AllocateMethodBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="c50e8-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="c50e8-103">Crea un búfer del tamaño especificado para un método y obtiene la dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="c50e8-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="c50e8-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="c50e8-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c50e8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c50e8-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c50e8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c50e8-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="c50e8-107">[in] La longitud del búfer que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c50e8-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="c50e8-108">[out] El búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="c50e8-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="c50e8-109">[out] La dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="c50e8-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c50e8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c50e8-110">Requirements</span></span>  
 <span data-ttu-id="c50e8-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c50e8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c50e8-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c50e8-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c50e8-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c50e8-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c50e8-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c50e8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c50e8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c50e8-115">See also</span></span>

- [<span data-ttu-id="c50e8-116">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c50e8-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
