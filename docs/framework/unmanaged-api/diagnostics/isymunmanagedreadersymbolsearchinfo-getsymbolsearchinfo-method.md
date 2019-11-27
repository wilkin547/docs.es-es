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
ms.openlocfilehash: 402b5b4bc9734be59ff342a4f86f2c4a1ed23b5f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446413"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="afb82-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="afb82-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="afb82-103">Obtiene la información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="afb82-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="afb82-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afb82-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="afb82-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="afb82-106">de `ULONG32` que indica el tamaño de `rgpSearchInfo`.</span><span class="sxs-lookup"><span data-stu-id="afb82-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="afb82-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener la información de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="afb82-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="afb82-108">enuncia Puntero que se establece en la interfaz [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="afb82-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afb82-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="afb82-109">Return Value</span></span>  
 <span data-ttu-id="afb82-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="afb82-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afb82-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="afb82-111">Requirements</span></span>  
 <span data-ttu-id="afb82-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="afb82-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb82-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="afb82-113">See also</span></span>

- [<span data-ttu-id="afb82-114">ISymUnmanagedReaderSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="afb82-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
