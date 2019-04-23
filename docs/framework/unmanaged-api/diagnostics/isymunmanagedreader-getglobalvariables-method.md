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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092648"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="d0277-102">ISymUnmanagedReader::GetGlobalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="d0277-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="d0277-103">Devuelve todas las variables globales.</span><span class="sxs-lookup"><span data-stu-id="d0277-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0277-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0277-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0277-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0277-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="d0277-106">[in] La longitud del búfer que apunta `pcVars`.</span><span class="sxs-lookup"><span data-stu-id="d0277-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="d0277-107">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener las variables.</span><span class="sxs-lookup"><span data-stu-id="d0277-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="d0277-108">[out] Un búfer que contiene las variables.</span><span class="sxs-lookup"><span data-stu-id="d0277-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0277-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d0277-109">Return Value</span></span>  
 <span data-ttu-id="d0277-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d0277-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0277-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0277-111">Requirements</span></span>  
 <span data-ttu-id="d0277-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d0277-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0277-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0277-113">See also</span></span>

- [<span data-ttu-id="d0277-114">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0277-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
