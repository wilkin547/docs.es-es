---
title: ICeeGen::GetIlSection (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
ms.openlocfilehash: c179d5e1ca976d8f425e7c408ceb663cba64f641
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715347"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="e7c66-102">ICeeGen::GetIlSection (Método)</span><span class="sxs-lookup"><span data-stu-id="e7c66-102">ICeeGen::GetIlSection Method</span></span>

<span data-ttu-id="e7c66-103">Obtiene la sección de la base de código de lenguaje intermedio a la que hace referencia el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="e7c66-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="e7c66-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="e7c66-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7c66-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7c66-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7c66-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7c66-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="e7c66-107">de Identificador de la sección que se va a obtener.</span><span class="sxs-lookup"><span data-stu-id="e7c66-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7c66-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7c66-108">Requirements</span></span>  

 <span data-ttu-id="e7c66-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7c66-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7c66-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e7c66-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7c66-111">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7c66-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7c66-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7c66-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7c66-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7c66-113">See also</span></span>

- [<span data-ttu-id="e7c66-114">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7c66-114">ICeeGen Interface</span></span>](iceegen-interface.md)
