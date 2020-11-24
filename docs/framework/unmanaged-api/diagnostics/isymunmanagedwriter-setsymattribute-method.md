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
ms.openlocfilehash: 484affb2ca87ca50a805d1bb46b7749d294d09f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683516"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="5eec0-102">ISymUnmanagedWriter::SetSymAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="5eec0-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>

<span data-ttu-id="5eec0-103">Define un atributo personalizado basado en su nombre.</span><span class="sxs-lookup"><span data-stu-id="5eec0-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="5eec0-104">Estos atributos se guardan en el almacén de símbolos, a diferencia de los atributos personalizados de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5eec0-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eec0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5eec0-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5eec0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5eec0-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="5eec0-107">de Token de metadatos para el que se define el atributo.</span><span class="sxs-lookup"><span data-stu-id="5eec0-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="5eec0-108">de Un puntero a un `WCHAR` que contiene el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="5eec0-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="5eec0-109">de `ULONG32` Que indica el tamaño de la `data` matriz.</span><span class="sxs-lookup"><span data-stu-id="5eec0-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="5eec0-110">de Valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="5eec0-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5eec0-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5eec0-111">Return Value</span></span>  

 <span data-ttu-id="5eec0-112">S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="5eec0-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eec0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5eec0-113">Requirements</span></span>  

 <span data-ttu-id="5eec0-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="5eec0-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eec0-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5eec0-115">See also</span></span>

- [<span data-ttu-id="5eec0-116">ISymUnmanagedWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5eec0-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
