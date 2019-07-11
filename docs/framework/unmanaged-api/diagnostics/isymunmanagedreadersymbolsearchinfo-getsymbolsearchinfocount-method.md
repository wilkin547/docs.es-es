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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1a72f76f1cd6f6571eaebff3a8046de8dcd3d74
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751455"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="520a1-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount (Método)</span><span class="sxs-lookup"><span data-stu-id="520a1-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="520a1-103">Obtiene un recuento de la información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="520a1-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="520a1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="520a1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="520a1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="520a1-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="520a1-106">] out] un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener la información de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="520a1-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="520a1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="520a1-107">Return Value</span></span>  
 <span data-ttu-id="520a1-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="520a1-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="520a1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="520a1-109">Requirements</span></span>  
 <span data-ttu-id="520a1-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="520a1-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="520a1-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="520a1-111">See also</span></span>

- [<span data-ttu-id="520a1-112">ISymUnmanagedReaderSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="520a1-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
