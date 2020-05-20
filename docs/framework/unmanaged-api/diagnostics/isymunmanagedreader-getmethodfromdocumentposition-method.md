---
title: ISymUnmanagedReader::GetMethodFromDocumentPosition (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
ms.openlocfilehash: 8015056b110fe8a5b5122b1bc81143980b780047
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614986"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="9cd13-102">ISymUnmanagedReader::GetMethodFromDocumentPosition (Método)</span><span class="sxs-lookup"><span data-stu-id="9cd13-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>
<span data-ttu-id="9cd13-103">Devuelve el método que contiene el punto de interrupción en la posición especificada de un documento.</span><span class="sxs-lookup"><span data-stu-id="9cd13-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cd13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9cd13-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cd13-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9cd13-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="9cd13-106">de Documento especificado.</span><span class="sxs-lookup"><span data-stu-id="9cd13-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="9cd13-107">de Línea del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="9cd13-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="9cd13-108">de Columna del documento especificado.</span><span class="sxs-lookup"><span data-stu-id="9cd13-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9cd13-109">enuncia Puntero a la dirección de un objeto de [interfaz ISymUnmanagedMethod](isymunmanagedmethod-interface.md) que representa el método que contiene el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="9cd13-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cd13-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9cd13-110">Return Value</span></span>  
 <span data-ttu-id="9cd13-111">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="9cd13-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cd13-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9cd13-112">Requirements</span></span>  
 <span data-ttu-id="9cd13-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9cd13-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cd13-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="9cd13-114">See also</span></span>

- [<span data-ttu-id="9cd13-115">ISymUnmanagedReader (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9cd13-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
