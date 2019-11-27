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
ms.openlocfilehash: 923a92ea256f79a1b0130b61c4fd99460fda96a0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441800"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="aecb6-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="aecb6-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="aecb6-103">Devuelve una matriz de métodos, cada uno de los cuales contiene el punto de interrupción en la posición especificada de un documento.</span><span class="sxs-lookup"><span data-stu-id="aecb6-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aecb6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aecb6-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="aecb6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aecb6-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="aecb6-106">de Documento especificado.</span><span class="sxs-lookup"><span data-stu-id="aecb6-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="aecb6-107">de Línea del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="aecb6-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="aecb6-108">de Columna del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="aecb6-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="aecb6-109">[in] Tamaño de la matriz `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="aecb6-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="aecb6-110">enuncia Puntero a una variable que recibe el número de elementos devueltos en la matriz de `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="aecb6-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="aecb6-111">enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) que representa un método que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="aecb6-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aecb6-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aecb6-112">Return Value</span></span>  
 <span data-ttu-id="aecb6-113">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="aecb6-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aecb6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aecb6-114">Requirements</span></span>  
 <span data-ttu-id="aecb6-115">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="aecb6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aecb6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="aecb6-116">See also</span></span>

- [<span data-ttu-id="aecb6-117">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aecb6-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
