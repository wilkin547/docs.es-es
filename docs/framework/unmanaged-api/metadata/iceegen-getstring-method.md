---
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
ms.openlocfilehash: b7b15261d825c1bd5f217c4cecd82ed36a716d0e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008266"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="e9569-102">ICeeGen::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="e9569-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="e9569-103">Obtiene la cadena almacenada en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="e9569-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="e9569-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="e9569-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9569-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9569-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9569-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9569-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="e9569-107">de Dirección virtual relativa de la cadena que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="e9569-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="e9569-108">enuncia La cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="e9569-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9569-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9569-109">Requirements</span></span>  
 <span data-ttu-id="e9569-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9569-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9569-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9569-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9569-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e9569-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9569-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9569-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9569-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9569-114">See also</span></span>

- [<span data-ttu-id="e9569-115">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9569-115">ICeeGen Interface</span></span>](iceegen-interface.md)
