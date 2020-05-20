---
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
ms.openlocfilehash: bba0fc039c403d45e8a5b60f2b0231eb24226280
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614960"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="2939c-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="2939c-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="2939c-103">Devuelve una matriz de métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada de un documento.</span><span class="sxs-lookup"><span data-stu-id="2939c-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2939c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2939c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2939c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2939c-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="2939c-106">de Documento especificado.</span><span class="sxs-lookup"><span data-stu-id="2939c-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="2939c-107">de Línea del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="2939c-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="2939c-108">de Columna del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="2939c-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="2939c-109">[in] Tamaño de la matriz `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="2939c-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="2939c-110">enuncia Puntero a una variable que recibe el número de elementos devueltos en la `pRetVal` matriz.</span><span class="sxs-lookup"><span data-stu-id="2939c-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="2939c-111">enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) que representa un método que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="2939c-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2939c-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2939c-112">Return Value</span></span>  
 <span data-ttu-id="2939c-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="2939c-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2939c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2939c-114">Requirements</span></span>  
 <span data-ttu-id="2939c-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2939c-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2939c-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="2939c-116">See also</span></span>

- [<span data-ttu-id="2939c-117">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2939c-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
