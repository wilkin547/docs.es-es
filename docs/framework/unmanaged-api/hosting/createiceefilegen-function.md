---
description: 'Más información acerca de: CreateICeeFileGen ((función)'
title: CreateICeeFileGen (Función)
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 10aefaad4dd1173e4ef55f727371bab508e2d40c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716938"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="8b0e0-103">CreateICeeFileGen (Función)</span><span class="sxs-lookup"><span data-stu-id="8b0e0-103">CreateICeeFileGen Function</span></span>

<span data-ttu-id="8b0e0-104">Crea un objeto [ICeeFileGen](iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="8b0e0-104">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="8b0e0-105">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8b0e0-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b0e0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b0e0-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b0e0-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b0e0-107">Parameters</span></span>  

 `ceeFileGen`  
 <span data-ttu-id="8b0e0-108">enuncia Puntero a la dirección de un nuevo `ICeeFileGen` objeto.</span><span class="sxs-lookup"><span data-stu-id="8b0e0-108">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b0e0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8b0e0-109">Return Value</span></span>  

 <span data-ttu-id="8b0e0-110">Este método devuelve los códigos de error COM estándar.</span><span class="sxs-lookup"><span data-stu-id="8b0e0-110">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b0e0-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8b0e0-111">Remarks</span></span>  

 <span data-ttu-id="8b0e0-112">El `ICeeFileGen` objeto se usa para crear archivos ejecutables portables (PE) de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8b0e0-112">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="8b0e0-113">Llame a la función [DestroyICeeFileGen (](destroyiceefilegen-function.md) para destruir el `ICeeFileGen` objeto cuando termine.</span><span class="sxs-lookup"><span data-stu-id="8b0e0-113">Call the [DestroyICeeFileGen](destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b0e0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b0e0-114">Requirements</span></span>  

 <span data-ttu-id="8b0e0-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b0e0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b0e0-116">**Encabezado:** ICeeFileGen. h</span><span class="sxs-lookup"><span data-stu-id="8b0e0-116">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="8b0e0-117">**Biblioteca:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="8b0e0-117">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="8b0e0-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b0e0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b0e0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b0e0-119">See also</span></span>

- [<span data-ttu-id="8b0e0-120">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="8b0e0-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
