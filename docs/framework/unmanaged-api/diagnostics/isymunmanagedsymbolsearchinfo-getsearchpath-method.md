---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPath (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 649f44bd7966b9ca89d2d040b7eede662404aa0f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093558"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="b2581-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath (Método)</span><span class="sxs-lookup"><span data-stu-id="b2581-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="b2581-103">Obtiene la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b2581-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2581-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2581-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2581-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2581-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="b2581-106">[out] Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b2581-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2581-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2581-107">Return Value</span></span>  
 <span data-ttu-id="b2581-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b2581-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2581-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2581-109">Requirements</span></span>  
 <span data-ttu-id="b2581-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b2581-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2581-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2581-111">See also</span></span>

- [<span data-ttu-id="b2581-112">ISymUnmanagedSymbolSearchInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2581-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
