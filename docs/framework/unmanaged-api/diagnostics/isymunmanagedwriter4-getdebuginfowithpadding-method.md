---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding (Método)
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: 274bf79175bda9e880b1ef3cf8f125a017ad0734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121669"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="577f2-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding (Método)</span><span class="sxs-lookup"><span data-stu-id="577f2-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="577f2-103">Funciona igual que el [método GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros después del carácter nulo de terminación para convertir los datos de cadena en un tamaño fijo de `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="577f2-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="577f2-104">El relleno solo se proporciona si la longitud de la cadena de ruta de acceso es menor que `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="577f2-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="577f2-105">Esto facilita la escritura de herramientas que diferencian los archivos PE.</span><span class="sxs-lookup"><span data-stu-id="577f2-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="577f2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="577f2-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="577f2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="577f2-107">Parameters</span></span>  
  
|<span data-ttu-id="577f2-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="577f2-108">Parameter</span></span>|<span data-ttu-id="577f2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="577f2-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="577f2-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="577f2-110">Return Value</span></span>  
 <span data-ttu-id="577f2-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="577f2-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="577f2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="577f2-112">Requirements</span></span>  
 <span data-ttu-id="577f2-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="577f2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="577f2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="577f2-114">See also</span></span>

- [<span data-ttu-id="577f2-115">ISymUnmanagedWriter4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="577f2-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
