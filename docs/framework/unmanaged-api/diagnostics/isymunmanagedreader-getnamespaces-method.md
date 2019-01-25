---
title: ISymUnmanagedReader::GetNamespaces (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5227de340bec85620f8c8d45538ad9a9d7f688fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630962"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="c1483-102">ISymUnmanagedReader::GetNamespaces (Método)</span><span class="sxs-lookup"><span data-stu-id="c1483-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="c1483-103">Obtiene los espacios de nombres definidos en el ámbito global dentro de este almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="c1483-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1483-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1483-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1483-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1483-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="c1483-106">[in] El tamaño de la matriz de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="c1483-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="c1483-107">[out] Un puntero a una variable que recibe la longitud de la lista de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c1483-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="c1483-108">[out] Un puntero a una variable que recibe la lista de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c1483-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1483-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c1483-109">Return Value</span></span>  
 <span data-ttu-id="c1483-110">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c1483-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1483-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1483-111">Requirements</span></span>  
 <span data-ttu-id="c1483-112">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c1483-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1483-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1483-113">See also</span></span>
- [<span data-ttu-id="c1483-114">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1483-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
