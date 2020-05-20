---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding (Método)
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: cfc6c22558cee780823c8cca0c36b883147e9496
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614648"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="c3056-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding (Método)</span><span class="sxs-lookup"><span data-stu-id="c3056-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="c3056-103">Funciona igual que el [método GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros después del carácter nulo de terminación para convertir los datos de cadena en un tamaño fijo de `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="c3056-103">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="c3056-104">El relleno solo se proporciona si la longitud de la cadena de ruta de acceso es menor que `MAX_PATH` .</span><span class="sxs-lookup"><span data-stu-id="c3056-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="c3056-105">Esto facilita la escritura de herramientas que diferencian los archivos PE.</span><span class="sxs-lookup"><span data-stu-id="c3056-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3056-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3056-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3056-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3056-107">Parameters</span></span>  
  
|<span data-ttu-id="c3056-108">Parámetro</span><span class="sxs-lookup"><span data-stu-id="c3056-108">Parameter</span></span>|<span data-ttu-id="c3056-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3056-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="c3056-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c3056-110">Return Value</span></span>  
 <span data-ttu-id="c3056-111">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="c3056-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3056-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3056-112">Requirements</span></span>  
 <span data-ttu-id="c3056-113">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="c3056-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3056-114">Consulta también</span><span class="sxs-lookup"><span data-stu-id="c3056-114">See also</span></span>

- [<span data-ttu-id="c3056-115">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c3056-115">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
