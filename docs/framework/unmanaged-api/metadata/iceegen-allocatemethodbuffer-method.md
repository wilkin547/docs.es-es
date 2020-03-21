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
ms.openlocfilehash: 38b9ea2ffab439f55f0a6d34d7f42c7669629168
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177920"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="0c1d7-102">ICeeGen::AllocateMethodBuffer (Método)</span><span class="sxs-lookup"><span data-stu-id="0c1d7-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="0c1d7-103">Crea un búfer del tamaño especificado para un método y obtiene la dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="0c1d7-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="0c1d7-104">Este método está obsoleto y no se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="0c1d7-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c1d7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c1d7-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c1d7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c1d7-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="0c1d7-107">[en] La longitud del búfer que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="0c1d7-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="0c1d7-108">[fuera] El búfer devuelto.</span><span class="sxs-lookup"><span data-stu-id="0c1d7-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="0c1d7-109">[fuera] La dirección virtual relativa del método.</span><span class="sxs-lookup"><span data-stu-id="0c1d7-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c1d7-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c1d7-110">Requirements</span></span>  
 <span data-ttu-id="0c1d7-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c1d7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c1d7-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c1d7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c1d7-113">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c1d7-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c1d7-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c1d7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c1d7-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0c1d7-115">See also</span></span>

- [<span data-ttu-id="0c1d7-116">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c1d7-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
