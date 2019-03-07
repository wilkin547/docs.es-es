---
title: ISymUnmanagedNamespace::GetVariables (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 02fd9fd3a580946cda09f0c129f02cd1218a0c9a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471438"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="195b8-102">ISymUnmanagedNamespace::GetVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="195b8-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="195b8-103">Devuelve todas las variables definidas en el ámbito global dentro de este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="195b8-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="195b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="195b8-104">Syntax</span></span>  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="195b8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="195b8-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="195b8-106">[in] Un `ULONG32` que indica el tamaño de la `pVars` matriz.</span><span class="sxs-lookup"><span data-stu-id="195b8-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="195b8-107">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="195b8-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="195b8-108">[out] Un puntero a un búfer que contiene los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="195b8-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="195b8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="195b8-109">Return Value</span></span>  
 <span data-ttu-id="195b8-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="195b8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="195b8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="195b8-111">Requirements</span></span>  
 <span data-ttu-id="195b8-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="195b8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195b8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="195b8-113">See also</span></span>
- [<span data-ttu-id="195b8-114">ISymUnmanagedNamespace (interfaz)</span><span class="sxs-lookup"><span data-stu-id="195b8-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
