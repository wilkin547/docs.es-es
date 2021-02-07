---
description: 'Más información sobre: ISymUnmanagedMethod:: Getsequencepoints ((método)'
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
ms.openlocfilehash: acdfcb014648593065bd1ae252ef936898a1e8b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721299"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="e77fe-103">ISymUnmanagedMethod::GetSequencePoints (Método)</span><span class="sxs-lookup"><span data-stu-id="e77fe-103">ISymUnmanagedMethod::GetSequencePoints Method</span></span>

<span data-ttu-id="e77fe-104">Obtiene todos los puntos de secuencia de este método.</span><span class="sxs-lookup"><span data-stu-id="e77fe-104">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e77fe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e77fe-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="e77fe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e77fe-106">Parameters</span></span>  

 `cPoints`  
 <span data-ttu-id="e77fe-107">de `ULONG32` Que recibe el tamaño de las `offsets` matrices, `documents` , `lines` , `columns` , `endLines` y `endColumns` .</span><span class="sxs-lookup"><span data-stu-id="e77fe-107">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="e77fe-108">enuncia Un puntero a un `ULONG32` que recibe la longitud del búfer necesario para contener los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="e77fe-108">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="e77fe-109">de Matriz en la que se almacenan los desplazamientos del lenguaje intermedio de Microsoft (MSIL) desde el principio del método para los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="e77fe-109">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="e77fe-110">de Matriz en la que se almacenan los documentos en los que se ubican los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="e77fe-110">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="e77fe-111">de Matriz en la que se almacenan las líneas de los documentos en las que se encuentran los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="e77fe-111">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="e77fe-112">de Matriz en la que se almacenan las columnas de los documentos en las que se encuentran los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="e77fe-112">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="e77fe-113">de Matriz de líneas de los documentos en las que finalizan los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="e77fe-113">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="e77fe-114">de Matriz de columnas de los documentos en las que finalizan los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="e77fe-114">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e77fe-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e77fe-115">Return Value</span></span>  

 <span data-ttu-id="e77fe-116">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e77fe-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e77fe-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e77fe-117">Requirements</span></span>  

 <span data-ttu-id="e77fe-118">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e77fe-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77fe-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e77fe-119">See also</span></span>

- [<span data-ttu-id="e77fe-120">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e77fe-120">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
