---
description: 'Más información sobre: ISymUnmanagedReaderSymbolSearchInfo:: Getsymbolsearchinfo ((método)'
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
ms.openlocfilehash: e14f78d6736684205b3f86150ce1fbb44a8112b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763610"
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="1dfe3-103">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="1dfe3-103">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>

<span data-ttu-id="1dfe3-104">Obtiene la información de búsqueda de símbolos.</span><span class="sxs-lookup"><span data-stu-id="1dfe3-104">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dfe3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dfe3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dfe3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1dfe3-106">Parameters</span></span>  

 `cSearchInfo`  
 <span data-ttu-id="1dfe3-107">de `ULONG32` Que indica el tamaño de `rgpSearchInfo` .</span><span class="sxs-lookup"><span data-stu-id="1dfe3-107">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="1dfe3-108">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener la información de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1dfe3-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="1dfe3-109">enuncia Puntero que se establece en la interfaz [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) devuelta.</span><span class="sxs-lookup"><span data-stu-id="1dfe3-109">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1dfe3-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1dfe3-110">Return Value</span></span>  

 <span data-ttu-id="1dfe3-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="1dfe3-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dfe3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1dfe3-112">Requirements</span></span>  

 <span data-ttu-id="1dfe3-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1dfe3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dfe3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dfe3-114">See also</span></span>

- [<span data-ttu-id="1dfe3-115">ISymUnmanagedReaderSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1dfe3-115">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)
