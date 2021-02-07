---
description: 'Más información sobre: ISymUnmanagedSymbolSearchInfo:: Getsearchpath ((método)'
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
ms.openlocfilehash: 2ae85733ccca8ac63fbca5d2556026221e5681bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763038"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="314af-103">ISymUnmanagedSymbolSearchInfo::GetSearchPath (Método)</span><span class="sxs-lookup"><span data-stu-id="314af-103">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>

<span data-ttu-id="314af-104">Obtiene la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="314af-104">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="314af-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="314af-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="314af-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="314af-106">Parameters</span></span>  

 `pcchPath`  
 <span data-ttu-id="314af-107">enuncia Un puntero a un `ULONG32` que recibe el tamaño, en caracteres, del búfer necesario para contener la ruta de acceso de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="314af-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="314af-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="314af-108">Return Value</span></span>  

 <span data-ttu-id="314af-109">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="314af-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="314af-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="314af-110">Requirements</span></span>  

 <span data-ttu-id="314af-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="314af-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="314af-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="314af-112">See also</span></span>

- [<span data-ttu-id="314af-113">ISymUnmanagedSymbolSearchInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="314af-113">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
