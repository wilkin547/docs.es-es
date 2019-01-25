---
title: ICeeGen::GetStringSection (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c4ccbff4a4967e7525ee4e51650a4f53e5458666
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605523"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="c9ba6-102">ICeeGen::GetStringSection (Método)</span><span class="sxs-lookup"><span data-stu-id="c9ba6-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="c9ba6-103">Obtiene una representación de cadena de la sección de código al que hace referencia el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="c9ba6-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="c9ba6-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="c9ba6-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9ba6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9ba6-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9ba6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9ba6-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="c9ba6-107">[in, out] El identificador de la sección de código.</span><span class="sxs-lookup"><span data-stu-id="c9ba6-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9ba6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9ba6-108">Requirements</span></span>  
 <span data-ttu-id="c9ba6-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9ba6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9ba6-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c9ba6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c9ba6-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c9ba6-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c9ba6-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9ba6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9ba6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9ba6-113">See also</span></span>
- [<span data-ttu-id="c9ba6-114">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9ba6-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
