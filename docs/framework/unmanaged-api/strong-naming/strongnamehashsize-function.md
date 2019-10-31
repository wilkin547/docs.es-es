---
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
ms.openlocfilehash: c656f73748faf8be7124be65f3ed455f2d5fd07a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105185"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="d1070-102">StrongNameHashSize (Función)</span><span class="sxs-lookup"><span data-stu-id="d1070-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="d1070-103">Obtiene el tamaño de búfer necesario para un hash mediante el algoritmo hash especificado.</span><span class="sxs-lookup"><span data-stu-id="d1070-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="d1070-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="d1070-104">This function has been deprecated.</span></span> <span data-ttu-id="d1070-105">Use el método [ICLRStrongName:: strongnamehashsize (](../hosting/iclrstrongname-strongnamehashsize-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d1070-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1070-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1070-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1070-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1070-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="d1070-108">de Algoritmo hash que se usa para calcular el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="d1070-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="d1070-109">enuncia Tamaño de búfer devuelto, en bytes.</span><span class="sxs-lookup"><span data-stu-id="d1070-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1070-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d1070-110">Return Value</span></span>  
 <span data-ttu-id="d1070-111">`true` cuando se complete correctamente; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d1070-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1070-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1070-112">Remarks</span></span>  
 <span data-ttu-id="d1070-113">Si la función `StrongNameHashSize` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="d1070-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1070-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1070-114">Requirements</span></span>  
 <span data-ttu-id="d1070-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1070-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1070-116">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d1070-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d1070-117">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d1070-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1070-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1070-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1070-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1070-119">See also</span></span>

- [<span data-ttu-id="d1070-120">StrongNameHashSize (método)</span><span class="sxs-lookup"><span data-stu-id="d1070-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="d1070-121">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d1070-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
