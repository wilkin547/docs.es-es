---
title: ISymUnmanagedWriter::Close (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
ms.openlocfilehash: 0a7ecd475a8031fedb2c8474593b45045fcc6fb9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610137"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="0ac42-102">ISymUnmanagedWriter::Close (Método)</span><span class="sxs-lookup"><span data-stu-id="0ac42-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="0ac42-103">Cierra el escritor de símbolos después de confirmar los símbolos en el almacén de símbolos.</span><span class="sxs-lookup"><span data-stu-id="0ac42-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac42-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ac42-104">Syntax</span></span>  
  
```cpp  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0ac42-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0ac42-105">Return Value</span></span>  
 <span data-ttu-id="0ac42-106">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="0ac42-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ac42-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0ac42-107">Remarks</span></span>  
 <span data-ttu-id="0ac42-108">Después de esta llamada, el escritor de símbolos deja de ser válido para actualizaciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="0ac42-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="0ac42-109">Para cerrar el escritor de símbolos sin confirmar los símbolos, utilice en su lugar el método [ISymUnmanagedWriter:: ABORT](isymunmanagedwriter-abort-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0ac42-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ac42-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ac42-110">Requirements</span></span>  
 <span data-ttu-id="0ac42-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="0ac42-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac42-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0ac42-112">See also</span></span>

- [<span data-ttu-id="0ac42-113">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0ac42-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
