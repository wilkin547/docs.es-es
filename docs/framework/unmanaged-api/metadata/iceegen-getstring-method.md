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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7ac5ef95ca3705b11cfda51d7fd1aca7400abc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443078"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="934ca-102">ICeeGen::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="934ca-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="934ca-103">Obtiene la cadena almacenada en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="934ca-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="934ca-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="934ca-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="934ca-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="934ca-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="934ca-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="934ca-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="934ca-107">[in] La dirección virtual relativa de la cadena para devolver.</span><span class="sxs-lookup"><span data-stu-id="934ca-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="934ca-108">[out] La cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="934ca-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="934ca-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="934ca-109">Requirements</span></span>  
 <span data-ttu-id="934ca-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="934ca-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="934ca-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="934ca-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="934ca-112">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="934ca-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="934ca-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="934ca-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="934ca-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="934ca-114">See Also</span></span>  
 [<span data-ttu-id="934ca-115">ICeeGen (interfaz)</span><span class="sxs-lookup"><span data-stu-id="934ca-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
