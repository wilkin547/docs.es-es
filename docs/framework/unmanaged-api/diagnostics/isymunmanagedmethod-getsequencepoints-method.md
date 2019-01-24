---
title: ISymUnmanagedMethod::GetSequencePoints (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf6528e8fe6a979db26ae44819bf34a36592ed6b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623630"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="a24e2-102">ISymUnmanagedMethod::GetSequencePoints (Método)</span><span class="sxs-lookup"><span data-stu-id="a24e2-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="a24e2-103">Obtiene todos los puntos de secuencia dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="a24e2-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a24e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a24e2-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a24e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a24e2-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="a24e2-106">[in] Un `ULONG32` que recibe el tamaño de la `offsets`, `documents`, `lines`, `columns`, `endLines`, y `endColumns` matrices.</span><span class="sxs-lookup"><span data-stu-id="a24e2-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="a24e2-107">[out] Un puntero a un `ULONG32` que recibe la longitud del búfer necesario para contener los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="a24e2-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="a24e2-108">[in] Una matriz de desplazamientos en los que se va a almacenar el intermedio de Microsoft desde el principio del método para los puntos de secuencia del lenguaje (MSIL).</span><span class="sxs-lookup"><span data-stu-id="a24e2-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="a24e2-109">[in] Matriz en la que se va a almacenar los documentos en el que se ubican los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="a24e2-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="a24e2-110">[in] Matriz en la que se almacenan las líneas de los documentos en el que se ubican los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="a24e2-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="a24e2-111">[in] Matriz en la que se va a almacenar las columnas en los documentos en el que se ubican los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="a24e2-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="a24e2-112">[in] Matriz de líneas de los documentos en las que la secuencia de puntos finales.</span><span class="sxs-lookup"><span data-stu-id="a24e2-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="a24e2-113">[in] Matriz de columnas de los documentos en las que la secuencia de puntos finales.</span><span class="sxs-lookup"><span data-stu-id="a24e2-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a24e2-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a24e2-114">Return Value</span></span>  
 <span data-ttu-id="a24e2-115">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="a24e2-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a24e2-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a24e2-116">Requirements</span></span>  
 <span data-ttu-id="a24e2-117">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a24e2-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24e2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a24e2-118">See also</span></span>
- [<span data-ttu-id="a24e2-119">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a24e2-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
