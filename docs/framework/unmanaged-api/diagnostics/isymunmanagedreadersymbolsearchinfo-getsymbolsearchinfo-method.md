---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 628d6fac45b046d9e8f26ad8777c38450da27a1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427423"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="47c53-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="47c53-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="47c53-103">Obtiene información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="47c53-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47c53-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47c53-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47c53-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="47c53-106">[in] A `ULONG32` que indica el tamaño de `rgpSearchInfo`.</span><span class="sxs-lookup"><span data-stu-id="47c53-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="47c53-107">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener la información de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="47c53-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="47c53-108">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="47c53-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47c53-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="47c53-109">Return Value</span></span>  
 <span data-ttu-id="47c53-110">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="47c53-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47c53-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47c53-111">Requirements</span></span>  
 <span data-ttu-id="47c53-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="47c53-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c53-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="47c53-113">See Also</span></span>  
 [<span data-ttu-id="47c53-114">ISymUnmanagedReaderSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="47c53-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
