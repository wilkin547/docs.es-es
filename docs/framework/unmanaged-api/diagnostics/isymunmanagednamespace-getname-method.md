---
title: "ISymUnmanagedNamespace::GetName (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace.GetName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37b29e71a9a1185a7080f71b1621a07dd7ae41a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="3d2b5-102">ISymUnmanagedNamespace::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="3d2b5-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="3d2b5-103">Obtiene el nombre de este espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3d2b5-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d2b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d2b5-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d2b5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d2b5-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3d2b5-106">[in] A `ULONG32` que indica el tamaño de la `szName` búfer.</span><span class="sxs-lookup"><span data-stu-id="3d2b5-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3d2b5-107">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener el nombre de espacio de nombres, incluida la terminación null.</span><span class="sxs-lookup"><span data-stu-id="3d2b5-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="3d2b5-108">[out] Un puntero a un búfer que contiene el nombre de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3d2b5-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d2b5-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3d2b5-109">Return Value</span></span>  
 <span data-ttu-id="3d2b5-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3d2b5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d2b5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d2b5-111">Requirements</span></span>  
 <span data-ttu-id="3d2b5-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3d2b5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d2b5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d2b5-113">See Also</span></span>  
 [<span data-ttu-id="3d2b5-114">ISymUnmanagedNamespace (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d2b5-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
