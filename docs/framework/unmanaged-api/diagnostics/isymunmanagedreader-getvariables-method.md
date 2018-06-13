---
title: ISymUnmanagedReader::GetVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74df7ee71fc541c35bc393f637ad1d7b9f7aa2a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425531"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="36ed8-102">ISymUnmanagedReader::GetVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="36ed8-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="36ed8-103">Devuelve una variable no local, según su elemento primario y su nombre.</span><span class="sxs-lookup"><span data-stu-id="36ed8-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36ed8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36ed8-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36ed8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36ed8-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="36ed8-106">[in] El elemento primario de la variable.</span><span class="sxs-lookup"><span data-stu-id="36ed8-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="36ed8-107">[in] Tamaño de la matriz `pVars`.</span><span class="sxs-lookup"><span data-stu-id="36ed8-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="36ed8-108">[out] Un puntero a la variable que recibe el número de variables devueltas en `pVars`.</span><span class="sxs-lookup"><span data-stu-id="36ed8-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="36ed8-109">[out] Un puntero a la variable que recibe las variables.</span><span class="sxs-lookup"><span data-stu-id="36ed8-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36ed8-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="36ed8-110">Return Value</span></span>  
 <span data-ttu-id="36ed8-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="36ed8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36ed8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36ed8-112">Requirements</span></span>  
 <span data-ttu-id="36ed8-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="36ed8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ed8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="36ed8-114">See Also</span></span>  
 [<span data-ttu-id="36ed8-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="36ed8-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
