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
ms.openlocfilehash: 68dc80c657c3794a416f6e142f70cfb05bee2c77
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745892"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="999fc-102">ICeeGen::GetStringSection (Método)</span><span class="sxs-lookup"><span data-stu-id="999fc-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="999fc-103">Obtiene una representación de cadena de la sección de código al que hace referencia el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="999fc-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="999fc-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="999fc-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="999fc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="999fc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="999fc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="999fc-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="999fc-107">[in, out] El identificador de la sección de código.</span><span class="sxs-lookup"><span data-stu-id="999fc-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="999fc-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="999fc-108">Requirements</span></span>  
 <span data-ttu-id="999fc-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="999fc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="999fc-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="999fc-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="999fc-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="999fc-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="999fc-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="999fc-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="999fc-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="999fc-113">See also</span></span>

- [<span data-ttu-id="999fc-114">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="999fc-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
