---
title: ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfoCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount
helpviewer_keywords:
- GetSymbolSearchInfoCount method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount method [.NET Framework debugging]
ms.assetid: 4068b6ec-525f-4446-8818-0296178cbd19
topic_type:
- apiref
ms.openlocfilehash: 5883b35bb3f1fec24ec108c9839501f0e81881fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708873"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="c5950-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount (Método)</span><span class="sxs-lookup"><span data-stu-id="c5950-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>

<span data-ttu-id="c5950-103">Obtiene un recuento de información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="c5950-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5950-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5950-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5950-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5950-105">Parameters</span></span>  

 `pcSearchInfo`  
 <span data-ttu-id="c5950-106">] out] un puntero a `ULONG32` que recibe el tamaño del búfer necesario para contener la información de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="c5950-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5950-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c5950-107">Return Value</span></span>  

 <span data-ttu-id="c5950-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c5950-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5950-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5950-109">Requirements</span></span>  

 <span data-ttu-id="c5950-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c5950-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5950-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5950-111">See also</span></span>

- [<span data-ttu-id="c5950-112">ISymUnmanagedReaderSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5950-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
