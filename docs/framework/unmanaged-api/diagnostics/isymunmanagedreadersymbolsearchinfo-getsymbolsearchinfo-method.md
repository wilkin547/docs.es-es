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
ms.openlocfilehash: 69e05fc33b3489f535f1d051da0294fe59e11e00
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708964"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="e9d86-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="e9d86-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>

<span data-ttu-id="e9d86-103">Obtiene la información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="e9d86-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9d86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9d86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9d86-105">Parameters</span></span>  

 `cSearchInfo`  
 <span data-ttu-id="e9d86-106">de `ULONG32` Que indica el tamaño de `rgpSearchInfo` .</span><span class="sxs-lookup"><span data-stu-id="e9d86-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="e9d86-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener la información de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e9d86-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="e9d86-108">enuncia Puntero que se establece en la interfaz [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="e9d86-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9d86-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e9d86-109">Return Value</span></span>  

 <span data-ttu-id="e9d86-110">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e9d86-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9d86-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9d86-111">Requirements</span></span>  

 <span data-ttu-id="e9d86-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e9d86-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d86-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9d86-113">See also</span></span>

- [<span data-ttu-id="e9d86-114">ISymUnmanagedReaderSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9d86-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
