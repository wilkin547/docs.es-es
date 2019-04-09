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
ms.openlocfilehash: 70d78942d4db2fea2cc1ccbcc5ddb20d743e9fdf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093675"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="7c870-102">ICeeGen::GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="7c870-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="7c870-103">Obtiene la cadena almacenada en la dirección virtual relativa especificada.</span><span class="sxs-lookup"><span data-stu-id="7c870-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="7c870-104">Este método está obsoleto y no debe usarse.</span><span class="sxs-lookup"><span data-stu-id="7c870-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c870-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c870-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c870-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c870-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="7c870-107">[in] La dirección virtual relativa de la cadena para devolver.</span><span class="sxs-lookup"><span data-stu-id="7c870-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="7c870-108">[out] La cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="7c870-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c870-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c870-109">Requirements</span></span>  
 <span data-ttu-id="7c870-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c870-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c870-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="7c870-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c870-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c870-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7c870-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7c870-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c870-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c870-114">See also</span></span>

- [<span data-ttu-id="7c870-115">ICeeGen (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c870-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
