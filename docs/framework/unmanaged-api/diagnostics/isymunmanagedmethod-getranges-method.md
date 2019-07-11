---
title: ISymUnmanagedMethod::GetRanges (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef5a98d510eee8942a2cad0525b6902e3e4eaa52
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769391"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="037af-102">ISymUnmanagedMethod::GetRanges (Método)</span><span class="sxs-lookup"><span data-stu-id="037af-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="037af-103">Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos de lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="037af-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="037af-104">La matriz es una matriz de enteros y tiene el formato [inicio, fin, inicio, final].</span><span class="sxs-lookup"><span data-stu-id="037af-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="037af-105">El número de pares del intervalo es la longitud de la matriz dividida por 2.</span><span class="sxs-lookup"><span data-stu-id="037af-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="037af-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="037af-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="037af-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="037af-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="037af-108">[in] El documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="037af-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="037af-109">[in] La línea del documento correspondiente a los intervalos.</span><span class="sxs-lookup"><span data-stu-id="037af-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="037af-110">[in] Columna del documento correspondiente a los intervalos.</span><span class="sxs-lookup"><span data-stu-id="037af-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="037af-111">[in] Tamaño de la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="037af-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="037af-112">[out] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los intervalos.</span><span class="sxs-lookup"><span data-stu-id="037af-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="037af-113">[out] Un puntero al búfer que recibe los intervalos.</span><span class="sxs-lookup"><span data-stu-id="037af-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="037af-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="037af-114">Return Value</span></span>  
 <span data-ttu-id="037af-115">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="037af-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="037af-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="037af-116">Requirements</span></span>  
 <span data-ttu-id="037af-117">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="037af-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="037af-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="037af-118">See also</span></span>

- [<span data-ttu-id="037af-119">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="037af-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
