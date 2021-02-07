---
description: 'Más información acerca de: ISymUnmanagedReader:: Getmethodsfromdocumentposition ((método)'
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: 033bdce2cd70e578ebd3be8a187d983a2c58b99d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764039"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="5f061-103">ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="5f061-103">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>

<span data-ttu-id="5f061-104">Devuelve una matriz de métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada de un documento.</span><span class="sxs-lookup"><span data-stu-id="5f061-104">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f061-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f061-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f061-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5f061-106">Parameters</span></span>  

 `document`  
 <span data-ttu-id="5f061-107">de Documento especificado.</span><span class="sxs-lookup"><span data-stu-id="5f061-107">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="5f061-108">de Línea del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="5f061-108">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="5f061-109">de Columna del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="5f061-109">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="5f061-110">[in] Tamaño de la matriz `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="5f061-110">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="5f061-111">enuncia Puntero a una variable que recibe el número de elementos devueltos en la `pRetVal` matriz.</span><span class="sxs-lookup"><span data-stu-id="5f061-111">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="5f061-112">enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) que representa un método que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5f061-112">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f061-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5f061-113">Return Value</span></span>  

 <span data-ttu-id="5f061-114">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5f061-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f061-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f061-115">Requirements</span></span>  

 <span data-ttu-id="5f061-116">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5f061-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f061-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f061-117">See also</span></span>

- [<span data-ttu-id="5f061-118">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f061-118">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
