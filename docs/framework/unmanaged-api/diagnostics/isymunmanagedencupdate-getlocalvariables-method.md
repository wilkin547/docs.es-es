---
title: "ISymUnmanagedENCUpdate::GetLocalVariables (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedENCUpdate.GetLocalVariables
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 492d41402531cb6fb92f90ab0e533fb20c6129df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="f06a3-102">ISymUnmanagedENCUpdate::GetLocalVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="f06a3-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="f06a3-103">Obtiene las variables locales.</span><span class="sxs-lookup"><span data-stu-id="f06a3-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f06a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f06a3-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f06a3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f06a3-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="f06a3-106">[in] El token de metadatos del método.</span><span class="sxs-lookup"><span data-stu-id="f06a3-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="f06a3-107">[in] A `ULONG` que indica el tamaño de la `rgLocals` parámetro.</span><span class="sxs-lookup"><span data-stu-id="f06a3-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="f06a3-108">[out] La matriz devuelta de <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable` instancias.</span><span class="sxs-lookup"><span data-stu-id="f06a3-108">[out] The returned array of <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable`  instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="f06a3-109">[out] Un puntero a un `ULONG` que recibe el tamaño de la `rgLocals` búfer necesario para contener las variables locales.</span><span class="sxs-lookup"><span data-stu-id="f06a3-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f06a3-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f06a3-110">Return Value</span></span>  
 <span data-ttu-id="f06a3-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f06a3-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f06a3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f06a3-112">Requirements</span></span>  
 <span data-ttu-id="f06a3-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f06a3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06a3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f06a3-114">See Also</span></span>  
 [<span data-ttu-id="f06a3-115">ISymUnmanagedENCUpdate (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f06a3-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
