---
description: 'Más información sobre: ISymUnmanagedMethod:: Getranges ((método)'
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
ms.openlocfilehash: e6a1da285c0574ef5910e8e727c3bcc5cb9e5d35
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790105"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="13fab-103">ISymUnmanagedMethod::GetRanges (Método)</span><span class="sxs-lookup"><span data-stu-id="13fab-103">ISymUnmanagedMethod::GetRanges Method</span></span>

<span data-ttu-id="13fab-104">Dada una posición en un documento, devuelve una matriz de pares de desplazamiento inicial y final que corresponden a los intervalos del lenguaje intermedio de Microsoft (MSIL) que cubre la posición dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="13fab-104">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="13fab-105">La matriz es una matriz de enteros y tiene el formato [Inicio, fin, Inicio, fin].</span><span class="sxs-lookup"><span data-stu-id="13fab-105">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="13fab-106">El número de pares de intervalo es la longitud de la matriz dividida entre 2.</span><span class="sxs-lookup"><span data-stu-id="13fab-106">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13fab-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13fab-107">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="13fab-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13fab-108">Parameters</span></span>  

 `document`  
 <span data-ttu-id="13fab-109">de Documento para el que se solicita el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="13fab-109">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="13fab-110">de Línea del documento correspondiente a los intervalos.</span><span class="sxs-lookup"><span data-stu-id="13fab-110">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="13fab-111">de Columna del documento correspondiente a los intervalos.</span><span class="sxs-lookup"><span data-stu-id="13fab-111">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="13fab-112">[in] Tamaño de la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="13fab-112">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="13fab-113">enuncia Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los intervalos.</span><span class="sxs-lookup"><span data-stu-id="13fab-113">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="13fab-114">enuncia Puntero al búfer que recibe los intervalos.</span><span class="sxs-lookup"><span data-stu-id="13fab-114">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13fab-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="13fab-115">Return Value</span></span>  

 <span data-ttu-id="13fab-116">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="13fab-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13fab-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13fab-117">Requirements</span></span>  

 <span data-ttu-id="13fab-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="13fab-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fab-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="13fab-119">See also</span></span>

- [<span data-ttu-id="13fab-120">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="13fab-120">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
