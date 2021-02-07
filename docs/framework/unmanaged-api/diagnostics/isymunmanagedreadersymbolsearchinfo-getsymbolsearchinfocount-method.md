---
description: 'Más información sobre: ISymUnmanagedReaderSymbolSearchInfo:: GetSymbolSearchInfoCount ((método)'
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
ms.openlocfilehash: b8bfa61397850c3f960fe30c0136e0a8b074cf1e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763597"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfocount-method"></a><span data-ttu-id="1a745-103">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount (Método)</span><span class="sxs-lookup"><span data-stu-id="1a745-103">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfoCount Method</span></span>

<span data-ttu-id="1a745-104">Obtiene un recuento de información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="1a745-104">Gets a count of symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a745-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a745-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfoCount(  
    [out] ULONG32 *pcSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a745-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a745-106">Parameters</span></span>  

 `pcSearchInfo`  
 <span data-ttu-id="1a745-107">] out] un puntero a `ULONG32` que recibe el tamaño del búfer necesario para contener la información de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1a745-107">]out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1a745-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1a745-108">Return Value</span></span>  

 <span data-ttu-id="1a745-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1a745-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a745-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a745-110">Requirements</span></span>  

 <span data-ttu-id="1a745-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1a745-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a745-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a745-112">See also</span></span>

- [<span data-ttu-id="1a745-113">ISymUnmanagedReaderSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a745-113">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
