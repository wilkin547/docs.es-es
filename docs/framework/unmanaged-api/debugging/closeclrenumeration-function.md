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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60b6d9c302cd3af9f41e5a8dce62d7eb268c4198
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961179"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="707d6-102">CloseCLREnumeration (Función)</span><span class="sxs-lookup"><span data-stu-id="707d6-102">CloseCLREnumeration Function</span></span>
<span data-ttu-id="707d6-103">Cierra los eventos de inicio continuo de common language runtime (CLR) válidos ubicados en una matriz de identificadores devueltos por la [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)y libera la memoria para las matrices de ruta de acceso de identificadores y cadenas.</span><span class="sxs-lookup"><span data-stu-id="707d6-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="707d6-104">Syntax</span></span>  
  
```  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="707d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="707d6-105">Parameters</span></span>  
 `pHandleArray`  
 <span data-ttu-id="707d6-106">[in] Puntero a la matriz de identificadores de eventos devueltos desde la [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="707d6-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="707d6-107">[in] Puntero a la matriz de rutas de acceso de cadena CLR devueltas desde el [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="707d6-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="707d6-108">[in] DWORD que contiene el tamaño (longitud) de `pHandleArray` o `pStringArray` (son iguales).</span><span class="sxs-lookup"><span data-stu-id="707d6-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="707d6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="707d6-109">Return Value</span></span>  
 <span data-ttu-id="707d6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="707d6-110">S_OK</span></span>  
 <span data-ttu-id="707d6-111">Identificadores abiertos por el [EnumerateCLRs (función)](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) están cerrados, y se libera la memoria asignada para las matrices de identificadores y cadenas.</span><span class="sxs-lookup"><span data-stu-id="707d6-111">Handles opened by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="707d6-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="707d6-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="707d6-113">La longitud de `pHandleArray` no coincide con la longitud que se pasa en `dwArrayLength`.</span><span class="sxs-lookup"><span data-stu-id="707d6-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="707d6-114">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="707d6-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="707d6-115">La función no puede liberar la memoria para `pHandleArray` y `pStringArray`.</span><span class="sxs-lookup"><span data-stu-id="707d6-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="707d6-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="707d6-116">Requirements</span></span>  
 <span data-ttu-id="707d6-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="707d6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="707d6-118">**Encabezado:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="707d6-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="707d6-119">**Biblioteca:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="707d6-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="707d6-120">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="707d6-120">**.NET Framework Versions:** 3.5 SP1</span></span>
