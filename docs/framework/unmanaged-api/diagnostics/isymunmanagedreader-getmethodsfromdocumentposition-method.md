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
ms.openlocfilehash: 5298dd0f53693d96b748f6c839660838fdfad4ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689555"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="b845a-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="b845a-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>

<span data-ttu-id="b845a-103">Devuelve una matriz de métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada de un documento.</span><span class="sxs-lookup"><span data-stu-id="b845a-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b845a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b845a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b845a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b845a-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="b845a-106">de Documento especificado.</span><span class="sxs-lookup"><span data-stu-id="b845a-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="b845a-107">de Línea del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="b845a-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="b845a-108">de Columna del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="b845a-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="b845a-109">[in] Tamaño de la matriz `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="b845a-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="b845a-110">enuncia Puntero a una variable que recibe el número de elementos devueltos en la `pRetVal` matriz.</span><span class="sxs-lookup"><span data-stu-id="b845a-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b845a-111">enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) que representa un método que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="b845a-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b845a-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b845a-112">Return Value</span></span>  

 <span data-ttu-id="b845a-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="b845a-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b845a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b845a-114">Requirements</span></span>  

 <span data-ttu-id="b845a-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b845a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b845a-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b845a-116">See also</span></span>

- [<span data-ttu-id="b845a-117">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b845a-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
