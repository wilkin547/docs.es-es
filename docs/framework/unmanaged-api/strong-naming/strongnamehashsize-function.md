---
description: 'Más información acerca de: Strongnamehashsize ((función)'
title: StrongNameHashSize (Función)
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
ms.openlocfilehash: 3e6700bfce3ba480814f3837011c5f8f7107bbd5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781251"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="08da8-103">StrongNameHashSize (Función)</span><span class="sxs-lookup"><span data-stu-id="08da8-103">StrongNameHashSize Function</span></span>

<span data-ttu-id="08da8-104">Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="08da8-104">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="08da8-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="08da8-105">This function has been deprecated.</span></span> <span data-ttu-id="08da8-106">Use el método [ICLRStrongName:: strongnamehashsize (](../hosting/iclrstrongname-strongnamehashsize-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="08da8-106">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08da8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08da8-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08da8-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08da8-108">Parameters</span></span>  

 `ulHashAlg`  
 <span data-ttu-id="08da8-109">de Algoritmo hash que se usa para calcular el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="08da8-109">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="08da8-110">enuncia Tamaño de búfer devuelto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="08da8-110">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08da8-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="08da8-111">Return Value</span></span>  

 <span data-ttu-id="08da8-112">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="08da8-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08da8-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="08da8-113">Remarks</span></span>  

 <span data-ttu-id="08da8-114">Si la `StrongNameHashSize` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="08da8-114">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08da8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08da8-115">Requirements</span></span>  

 <span data-ttu-id="08da8-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08da8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08da8-117">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="08da8-117">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="08da8-118">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08da8-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08da8-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08da8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08da8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="08da8-120">See also</span></span>

- [<span data-ttu-id="08da8-121">Método StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="08da8-121">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="08da8-122">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08da8-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
