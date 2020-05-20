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
ms.openlocfilehash: 451cfecde7e14fad9d3fed3367112e1fb59796e5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615150"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="c8cf8-102">ISymUnmanagedMethod::GetSequencePoints (Método)</span><span class="sxs-lookup"><span data-stu-id="c8cf8-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="c8cf8-103">Obtiene todos los puntos de secuencia de este método.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8cf8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8cf8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c8cf8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c8cf8-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="c8cf8-106">de `ULONG32`Que recibe el tamaño de las `offsets` matrices, `documents` , `lines` , `columns` , `endLines` y `endColumns` .</span><span class="sxs-lookup"><span data-stu-id="c8cf8-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="c8cf8-107">enuncia Un puntero a un `ULONG32` que recibe la longitud del búfer necesario para contener los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="c8cf8-108">de Matriz en la que se almacenan los desplazamientos del lenguaje intermedio de Microsoft (MSIL) desde el principio del método para los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="c8cf8-109">de Matriz en la que se almacenan los documentos en los que se ubican los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="c8cf8-110">de Matriz en la que se almacenan las líneas de los documentos en las que se encuentran los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="c8cf8-111">de Matriz en la que se almacenan las columnas de los documentos en las que se encuentran los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="c8cf8-112">de Matriz de líneas de los documentos en las que finalizan los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="c8cf8-113">de Matriz de columnas de los documentos en las que finalizan los puntos de secuencia.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8cf8-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c8cf8-114">Return Value</span></span>  
 <span data-ttu-id="c8cf8-115">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="c8cf8-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8cf8-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8cf8-116">Requirements</span></span>  
 <span data-ttu-id="c8cf8-117">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c8cf8-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8cf8-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="c8cf8-118">See also</span></span>

- [<span data-ttu-id="c8cf8-119">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c8cf8-119">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
