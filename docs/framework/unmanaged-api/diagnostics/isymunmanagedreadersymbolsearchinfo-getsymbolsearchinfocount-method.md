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
ms.openlocfilehash: 0b59d85227f21bb230333456eda9130416563111
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986302"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="f8a07-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount (Método)</span><span class="sxs-lookup"><span data-stu-id="f8a07-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>
<span data-ttu-id="f8a07-103">Obtiene un recuento de la información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="f8a07-103">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8a07-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8a07-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8a07-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8a07-105">Parameters</span></span>  
 `pcSearchInfo`  
 <span data-ttu-id="f8a07-106">] out] un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener la información de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f8a07-106">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8a07-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f8a07-107">Return Value</span></span>  
 <span data-ttu-id="f8a07-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f8a07-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8a07-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8a07-109">Requirements</span></span>  
 <span data-ttu-id="f8a07-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f8a07-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a07-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8a07-111">See also</span></span>

- [<span data-ttu-id="f8a07-112">ISymUnmanagedReaderSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8a07-112">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
