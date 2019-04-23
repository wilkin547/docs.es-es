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
ms.openlocfilehash: 846ff76fb1073394cc27597c9a2015148581cc70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165105"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="8e93d-102">ISymUnmanagedReader::GetVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="8e93d-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="8e93d-103">Devuelve una variable no local, dado su elemento primario y su nombre.</span><span class="sxs-lookup"><span data-stu-id="8e93d-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e93d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e93d-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e93d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e93d-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="8e93d-106">[in] El elemento primario de la variable.</span><span class="sxs-lookup"><span data-stu-id="8e93d-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="8e93d-107">[in] Tamaño de la matriz `pVars`.</span><span class="sxs-lookup"><span data-stu-id="8e93d-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="8e93d-108">[out] Un puntero a la variable que recibe el número de variables devueltas en `pVars`.</span><span class="sxs-lookup"><span data-stu-id="8e93d-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="8e93d-109">[out] Un puntero a la variable que recibe las variables.</span><span class="sxs-lookup"><span data-stu-id="8e93d-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e93d-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8e93d-110">Return Value</span></span>  
 <span data-ttu-id="8e93d-111">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8e93d-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e93d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e93d-112">Requirements</span></span>  
 <span data-ttu-id="8e93d-113">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8e93d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e93d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e93d-114">See also</span></span>

- [<span data-ttu-id="8e93d-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e93d-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
