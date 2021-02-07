---
description: 'Más información sobre: ICeeGen:: GetStringSection ((método)'
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
ms.openlocfilehash: ef4b4bb502e1099b9b3bcdbd494d03df0858aa6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721065"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="3cb25-103">ICeeGen::GetStringSection (Método)</span><span class="sxs-lookup"><span data-stu-id="3cb25-103">ICeeGen::GetStringSection Method</span></span>

<span data-ttu-id="3cb25-104">Obtiene una representación de cadena de la sección de código a la que hace referencia el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="3cb25-104">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="3cb25-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="3cb25-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cb25-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cb25-106">Syntax</span></span>  
  
```cpp  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cb25-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3cb25-107">Parameters</span></span>  

 `section`  
 <span data-ttu-id="3cb25-108">[in, out] Identificador de la sección de código.</span><span class="sxs-lookup"><span data-stu-id="3cb25-108">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cb25-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cb25-109">Requirements</span></span>  

 <span data-ttu-id="3cb25-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cb25-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cb25-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3cb25-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3cb25-112">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3cb25-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3cb25-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cb25-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cb25-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cb25-114">See also</span></span>

- [<span data-ttu-id="3cb25-115">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3cb25-115">ICeeGen Interface</span></span>](iceegen-interface.md)
