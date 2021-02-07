---
description: 'Más información acerca de: ISymUnmanagedWriter:: SetMethodSourceRange ((método)'
title: ISymUnmanagedWriter::SetMethodSourceRange (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetMethodSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetMethodSourceRange
helpviewer_keywords:
- SetMethodSourceRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetMethodSourceRange method [.NET Framework debugging]
ms.assetid: c698b86e-ace7-4b21-9549-f52d6a034959
topic_type:
- apiref
ms.openlocfilehash: 2e2f0f664d8be30a8c3628100fafb3740d34f54f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762076"
---
# <a name="isymunmanagedwritersetmethodsourcerange-method"></a><span data-ttu-id="da2e6-103">ISymUnmanagedWriter::SetMethodSourceRange (Método)</span><span class="sxs-lookup"><span data-stu-id="da2e6-103">ISymUnmanagedWriter::SetMethodSourceRange Method</span></span>

<span data-ttu-id="da2e6-104">Especifica el principio y final reales de un método dentro de un archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="da2e6-104">Specifies the true start and end of a method within a source file.</span></span> <span data-ttu-id="da2e6-105">Utilice este método para especificar la extensión de un método independientemente de los puntos de secuencia que existen dentro del método.</span><span class="sxs-lookup"><span data-stu-id="da2e6-105">Use this method to specify the extent of a method independently of the sequence points that exist within the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2e6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da2e6-106">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodSourceRange(  
    [in] ISymUnmanagedDocumentWriter  *startDoc,  
    [in] ULONG32                      startLine,  
    [in] ULONG32                      startColumn,  
    [in] ISymUnmanagedDocumentWriter  *endDoc,  
    [in] ULONG32                      endLine,  
    [in] ULONG32                      endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da2e6-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da2e6-107">Parameters</span></span>  

 `startDoc`  
 <span data-ttu-id="da2e6-108">de Puntero al documento que contiene la posición inicial.</span><span class="sxs-lookup"><span data-stu-id="da2e6-108">[in] A pointer to the document containing the starting position.</span></span>  
  
 `startLine`  
 <span data-ttu-id="da2e6-109">de Número de línea inicial.</span><span class="sxs-lookup"><span data-stu-id="da2e6-109">[in] The starting line number.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="da2e6-110">de Columna inicial.</span><span class="sxs-lookup"><span data-stu-id="da2e6-110">[in] The starting column.</span></span>  
  
 `endDoc`  
 <span data-ttu-id="da2e6-111">de Puntero al documento que contiene la posición final.</span><span class="sxs-lookup"><span data-stu-id="da2e6-111">[in] A pointer to the document containing the ending position.</span></span>  
  
 `endLine`  
 <span data-ttu-id="da2e6-112">de El número de línea final.</span><span class="sxs-lookup"><span data-stu-id="da2e6-112">[in] The ending line number.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="da2e6-113">de Número de la columna final.</span><span class="sxs-lookup"><span data-stu-id="da2e6-113">[in] The ending column number.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da2e6-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="da2e6-114">Return Value</span></span>  

 <span data-ttu-id="da2e6-115">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="da2e6-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da2e6-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da2e6-116">Requirements</span></span>  

 <span data-ttu-id="da2e6-117">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="da2e6-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da2e6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="da2e6-118">See also</span></span>

- [<span data-ttu-id="da2e6-119">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="da2e6-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
