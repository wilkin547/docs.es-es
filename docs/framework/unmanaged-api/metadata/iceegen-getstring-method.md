---
description: 'Más información acerca de: ICeeGen:: GetString (método)'
title: ICeeGen::GetString (Método)
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: 227b4badff3265fc22f1c76301ba03e58fea34c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706908"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="6629a-103">ICeeGen::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="6629a-103">ICeeGen::GetString Method</span></span>

<span data-ttu-id="6629a-104">Obtiene la cadena almacenada en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="6629a-104">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="6629a-105">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="6629a-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6629a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6629a-106">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6629a-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6629a-107">Parameters</span></span>  

 `RVA`  
 <span data-ttu-id="6629a-108">de Dirección virtual relativa de la cadena que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="6629a-108">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="6629a-109">enuncia La cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="6629a-109">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6629a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6629a-110">Requirements</span></span>  

 <span data-ttu-id="6629a-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6629a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6629a-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6629a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6629a-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6629a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6629a-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6629a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6629a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="6629a-115">See also</span></span>

- [<span data-ttu-id="6629a-116">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6629a-116">ICeeGen Interface</span></span>](iceegen-interface.md)
