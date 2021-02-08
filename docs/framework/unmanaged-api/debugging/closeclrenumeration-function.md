---
description: 'Más información acerca de: Closeclrenumeration ((función)'
title: CloseCLREnumeration (Función)
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
ms.openlocfilehash: 7669332cc23b78afbb3bf597e7d208a5f707aae5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772775"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="3cbea-103">CloseCLREnumeration (Función)</span><span class="sxs-lookup"><span data-stu-id="3cbea-103">CloseCLREnumeration Function</span></span>

<span data-ttu-id="3cbea-104">Cierra cualquier evento válido de Common Language Runtime (CLR) continue-startup ubicado en una matriz de identificadores devueltos por la [función enumerateclrs (](enumerateclrs-function.md)y libera la memoria para las matrices de rutas de acceso de identificador y de cadena.</span><span class="sxs-lookup"><span data-stu-id="3cbea-104">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cbea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cbea-105">Syntax</span></span>  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cbea-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3cbea-106">Parameters</span></span>  

 `pHandleArray`  
 <span data-ttu-id="3cbea-107">de Puntero a la matriz de identificadores de eventos devueltos por la [función enumerateclrs (](enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="3cbea-107">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="3cbea-108">de Puntero a la matriz de rutas de acceso de cadena CLR devuelta desde la [función enumerateclrs (](enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="3cbea-108">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="3cbea-109">[in] DWORD que contiene el tamaño (longitud) de `pHandleArray` o `pStringArray` (son iguales).</span><span class="sxs-lookup"><span data-stu-id="3cbea-109">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3cbea-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3cbea-110">Return Value</span></span>  

 <span data-ttu-id="3cbea-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3cbea-111">S_OK</span></span>  
 <span data-ttu-id="3cbea-112">Los identificadores abiertos por la [función enumerateclrs (](enumerateclrs-function.md) se cierran y se libera la memoria asignada para el identificador y las matrices de cadenas.</span><span class="sxs-lookup"><span data-stu-id="3cbea-112">Handles opened by the [EnumerateCLRs function](enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="3cbea-113">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3cbea-113">E_INVALIDARG</span></span>  
 <span data-ttu-id="3cbea-114">La longitud de `pHandleArray` no coincide con la longitud que se pasa en `dwArrayLength`.</span><span class="sxs-lookup"><span data-stu-id="3cbea-114">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="3cbea-115">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="3cbea-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="3cbea-116">La función no puede liberar la memoria para `pHandleArray` y `pStringArray`.</span><span class="sxs-lookup"><span data-stu-id="3cbea-116">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cbea-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cbea-117">Requirements</span></span>  

 <span data-ttu-id="3cbea-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cbea-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cbea-119">**Encabezado:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="3cbea-119">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="3cbea-120">**Biblioteca:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="3cbea-120">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="3cbea-121">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="3cbea-121">**.NET Framework Versions:** 3.5 SP1</span></span>
