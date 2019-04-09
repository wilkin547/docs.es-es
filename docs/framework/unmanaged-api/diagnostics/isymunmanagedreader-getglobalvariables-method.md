---
title: ISymUnmanagedReader::GetGlobalVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e778a5a7baed52941a7f4b990b34d31f8ca84c24
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092648"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="738b9-102">ISymUnmanagedReader::GetGlobalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="738b9-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="738b9-103">Devuelve todas las variables globales.</span><span class="sxs-lookup"><span data-stu-id="738b9-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="738b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="738b9-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="738b9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="738b9-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="738b9-106">[in] La longitud del búfer que apunta `pcVars`.</span><span class="sxs-lookup"><span data-stu-id="738b9-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="738b9-107">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener las variables.</span><span class="sxs-lookup"><span data-stu-id="738b9-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="738b9-108">[out] Un búfer que contiene las variables.</span><span class="sxs-lookup"><span data-stu-id="738b9-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="738b9-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="738b9-109">Return Value</span></span>  
 <span data-ttu-id="738b9-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="738b9-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="738b9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="738b9-111">Requirements</span></span>  
 <span data-ttu-id="738b9-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="738b9-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="738b9-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="738b9-113">See also</span></span>

- [<span data-ttu-id="738b9-114">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="738b9-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
