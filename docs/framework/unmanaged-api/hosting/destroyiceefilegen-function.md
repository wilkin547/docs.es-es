---
title: DestroyICeeFileGen (Función)
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
ms.openlocfilehash: ff7e7b299d185b8db263d2076c1e075b87b487fc
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616403"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="edec7-102">DestroyICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="edec7-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="edec7-103">Destruye un objeto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="edec7-103">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="edec7-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="edec7-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edec7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edec7-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edec7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="edec7-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="edec7-107">de `ICeeFileGen`Objeto que se va a destruir.</span><span class="sxs-lookup"><span data-stu-id="edec7-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="edec7-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="edec7-108">Return Value</span></span>  
 <span data-ttu-id="edec7-109">Este método devuelve los códigos de error COM estándar.</span><span class="sxs-lookup"><span data-stu-id="edec7-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edec7-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="edec7-110">Remarks</span></span>  
 <span data-ttu-id="edec7-111">`DestroyICeeFileGen`destruye el `ICeeFileGen` objeto creado por la función [CreateICeeFileGen (](createiceefilegen-function.md) .</span><span class="sxs-lookup"><span data-stu-id="edec7-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edec7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="edec7-112">Requirements</span></span>  
 <span data-ttu-id="edec7-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edec7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edec7-114">**Encabezado:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="edec7-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="edec7-115">**Biblioteca:** MSCorPE. dll</span><span class="sxs-lookup"><span data-stu-id="edec7-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="edec7-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edec7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edec7-117">Consulta también</span><span class="sxs-lookup"><span data-stu-id="edec7-117">See also</span></span>

- [<span data-ttu-id="edec7-118">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="edec7-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
