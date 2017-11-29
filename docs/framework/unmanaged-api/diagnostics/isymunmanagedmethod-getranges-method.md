---
title: "ISymUnmanagedMethod::GetRanges (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetRanges
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71d24bc83d6a26c800d0d97e885b322cc2b4ccbd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="2d596-102">ISymUnmanagedMethod::GetRanges (Método)</span><span class="sxs-lookup"><span data-stu-id="2d596-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="2d596-103">Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos del lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="2d596-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="2d596-104">La matriz es una matriz de enteros y tiene el formato [inicio, fin, inicio, final].</span><span class="sxs-lookup"><span data-stu-id="2d596-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="2d596-105">El número de pares del intervalo es la longitud de la matriz dividida entre 2.</span><span class="sxs-lookup"><span data-stu-id="2d596-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d596-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2d596-106">Syntax</span></span>  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d596-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2d596-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="2d596-108">[in] El documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="2d596-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="2d596-109">[in] La línea del documento correspondiente a los intervalos.</span><span class="sxs-lookup"><span data-stu-id="2d596-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="2d596-110">[in] Columna del documento correspondiente a los intervalos.</span><span class="sxs-lookup"><span data-stu-id="2d596-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="2d596-111">[in] Tamaño de la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="2d596-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="2d596-112">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los intervalos.</span><span class="sxs-lookup"><span data-stu-id="2d596-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="2d596-113">[out] Un puntero al búfer que recibe los intervalos.</span><span class="sxs-lookup"><span data-stu-id="2d596-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d596-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2d596-114">Return Value</span></span>  
 <span data-ttu-id="2d596-115">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2d596-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d596-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d596-116">Requirements</span></span>  
 <span data-ttu-id="2d596-117">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2d596-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d596-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d596-118">See Also</span></span>  
 [<span data-ttu-id="2d596-119">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2d596-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
