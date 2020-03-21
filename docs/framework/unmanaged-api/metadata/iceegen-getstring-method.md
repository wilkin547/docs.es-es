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
ms.openlocfilehash: ada126b41f1c634f7d8daa58480406ac26f92377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177907"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="4d8e1-102">ICeeGen::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="4d8e1-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="4d8e1-103">Obtiene la cadena almacenada en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="4d8e1-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="4d8e1-104">Este método está obsoleto y no se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="4d8e1-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d8e1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d8e1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d8e1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d8e1-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="4d8e1-107">[en] La dirección virtual relativa de la cadena que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="4d8e1-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="4d8e1-108">[fuera] La cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="4d8e1-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d8e1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d8e1-109">Requirements</span></span>  
 <span data-ttu-id="4d8e1-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d8e1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d8e1-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4d8e1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d8e1-112">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4d8e1-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4d8e1-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d8e1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d8e1-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d8e1-114">See also</span></span>

- [<span data-ttu-id="4d8e1-115">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d8e1-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
