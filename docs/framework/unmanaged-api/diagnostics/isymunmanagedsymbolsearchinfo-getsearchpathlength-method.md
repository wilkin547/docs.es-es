---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type:
- apiref
ms.openlocfilehash: 0be7297fbb71302035e71fbbf2c8b5e2a7faa2da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615298"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="3bf63-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength (Método)</span><span class="sxs-lookup"><span data-stu-id="3bf63-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="3bf63-103">Obtiene la longitud de la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3bf63-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bf63-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bf63-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bf63-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bf63-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="3bf63-106">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la longitud de la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="3bf63-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bf63-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3bf63-107">Return Value</span></span>  
 <span data-ttu-id="3bf63-108">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3bf63-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bf63-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bf63-109">Requirements</span></span>  
 <span data-ttu-id="3bf63-110">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3bf63-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf63-111">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3bf63-111">See also</span></span>

- [<span data-ttu-id="3bf63-112">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bf63-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
