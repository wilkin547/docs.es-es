---
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
ms.openlocfilehash: 575e194cf952f02a3fe4fce9e955e45e1bc3653d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673918"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="97542-102">CloseCLREnumeration (Función)</span><span class="sxs-lookup"><span data-stu-id="97542-102">CloseCLREnumeration Function</span></span>

<span data-ttu-id="97542-103">Cierra cualquier evento válido de Common Language Runtime (CLR) continue-startup ubicado en una matriz de identificadores devueltos por la [función enumerateclrs (](enumerateclrs-function.md)y libera la memoria para las matrices de rutas de acceso de identificador y de cadena.</span><span class="sxs-lookup"><span data-stu-id="97542-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97542-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97542-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97542-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="97542-105">Parameters</span></span>  

 `pHandleArray`  
 <span data-ttu-id="97542-106">de Puntero a la matriz de identificadores de eventos devueltos por la [función enumerateclrs (](enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="97542-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="97542-107">de Puntero a la matriz de rutas de acceso de cadena CLR devuelta desde la [función enumerateclrs (](enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="97542-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="97542-108">[in] DWORD que contiene el tamaño (longitud) de `pHandleArray` o `pStringArray` (son iguales).</span><span class="sxs-lookup"><span data-stu-id="97542-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97542-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="97542-109">Return Value</span></span>  

 <span data-ttu-id="97542-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="97542-110">S_OK</span></span>  
 <span data-ttu-id="97542-111">Los identificadores abiertos por la [función enumerateclrs (](enumerateclrs-function.md) se cierran y se libera la memoria asignada para el identificador y las matrices de cadenas.</span><span class="sxs-lookup"><span data-stu-id="97542-111">Handles opened by the [EnumerateCLRs function](enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="97542-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="97542-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="97542-113">La longitud de `pHandleArray` no coincide con la longitud que se pasa en `dwArrayLength`.</span><span class="sxs-lookup"><span data-stu-id="97542-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="97542-114">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="97542-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="97542-115">La función no puede liberar la memoria para `pHandleArray` y `pStringArray`.</span><span class="sxs-lookup"><span data-stu-id="97542-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97542-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97542-116">Requirements</span></span>  

 <span data-ttu-id="97542-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97542-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97542-118">**Encabezado:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="97542-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="97542-119">**Biblioteca:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="97542-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="97542-120">**.NET Framework versiones:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="97542-120">**.NET Framework Versions:** 3.5 SP1</span></span>
