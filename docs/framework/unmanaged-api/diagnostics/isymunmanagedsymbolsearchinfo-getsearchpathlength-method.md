---
description: 'Más información sobre: ISymUnmanagedSymbolSearchInfo:: GetSearchPathLength ((método)'
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
ms.openlocfilehash: 3d5faf9d972881ff9c1eaf71bcaa6f68da46dae6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763025"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="7fbfd-103">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength (Método)</span><span class="sxs-lookup"><span data-stu-id="7fbfd-103">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>

<span data-ttu-id="7fbfd-104">Obtiene la longitud de la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7fbfd-104">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fbfd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fbfd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fbfd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7fbfd-106">Parameters</span></span>  

 `pcchPath`  
 <span data-ttu-id="7fbfd-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la longitud de la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7fbfd-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7fbfd-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7fbfd-108">Return Value</span></span>  

 <span data-ttu-id="7fbfd-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="7fbfd-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fbfd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7fbfd-110">Requirements</span></span>  

 <span data-ttu-id="7fbfd-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7fbfd-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fbfd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fbfd-112">See also</span></span>

- [<span data-ttu-id="7fbfd-113">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7fbfd-113">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
