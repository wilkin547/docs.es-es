---
title: GetRealProcAddress (Función)
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
ms.openlocfilehash: 6bbf8366054c58543444a4b710a687198f365e6e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617209"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="b247c-102">GetRealProcAddress (Función)</span><span class="sxs-lookup"><span data-stu-id="b247c-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="b247c-103">Obtiene la dirección de la función especificada que se exporta de la última versión instalada del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b247c-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="b247c-104">Esta función está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="b247c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b247c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b247c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b247c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b247c-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="b247c-107">de Nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="b247c-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="b247c-108">enuncia La ubicación que recibe un puntero a la dirección de la función.</span><span class="sxs-lookup"><span data-stu-id="b247c-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b247c-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b247c-109">Return Value</span></span>  
 <span data-ttu-id="b247c-110">Este método devuelve los códigos de error del modelo de objetos componentes (COM) estándar, tal y como se define en WinError. h, además de los siguientes valores definidos en CorError. h.</span><span class="sxs-lookup"><span data-stu-id="b247c-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="b247c-111">Código de retorno</span><span class="sxs-lookup"><span data-stu-id="b247c-111">Return code</span></span>|<span data-ttu-id="b247c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b247c-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b247c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b247c-113">S_OK</span></span>|<span data-ttu-id="b247c-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b247c-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b247c-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b247c-115">E_POINTER</span></span>|<span data-ttu-id="b247c-116">`ppv` no es válido.</span><span class="sxs-lookup"><span data-stu-id="b247c-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="b247c-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="b247c-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="b247c-118">La función no se exporta desde el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b247c-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b247c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b247c-119">Requirements</span></span>  
 <span data-ttu-id="b247c-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b247c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b247c-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b247c-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b247c-122">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b247c-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b247c-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b247c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b247c-124">Consulta también</span><span class="sxs-lookup"><span data-stu-id="b247c-124">See also</span></span>

- [<span data-ttu-id="b247c-125">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="b247c-125">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
