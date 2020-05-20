---
title: ISymUnmanagedWriter::SetSymAttribute (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
ms.openlocfilehash: 39b0c065a324f2b3939467901739f995bc9abbad
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614765"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="f56cc-102">ISymUnmanagedWriter::SetSymAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="f56cc-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="f56cc-103">Define un atributo personalizado basado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="f56cc-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="f56cc-104">Estos atributos se guardan en el almacén de símbolos, a diferencia de los atributos personalizados de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f56cc-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f56cc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f56cc-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f56cc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f56cc-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="f56cc-107">de Token de metadatos para el que se define el atributo.</span><span class="sxs-lookup"><span data-stu-id="f56cc-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="f56cc-108">de Un puntero a un `WCHAR` que contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="f56cc-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="f56cc-109">de `ULONG32`Que indica el tamaño de la `data` matriz.</span><span class="sxs-lookup"><span data-stu-id="f56cc-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="f56cc-110">de Valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="f56cc-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f56cc-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f56cc-111">Return Value</span></span>  
 <span data-ttu-id="f56cc-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="f56cc-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f56cc-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f56cc-113">Requirements</span></span>  
 <span data-ttu-id="f56cc-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f56cc-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f56cc-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="f56cc-115">See also</span></span>

- [<span data-ttu-id="f56cc-116">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f56cc-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
