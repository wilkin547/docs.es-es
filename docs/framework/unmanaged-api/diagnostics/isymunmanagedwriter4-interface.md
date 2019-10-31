---
title: ISymUnmanagedWriter4 (Interfaz)
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: a656777461c50b5a1593917278eb54abda982dc2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134560"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="b4495-102">ISymUnmanagedWriter4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4495-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="b4495-103">Interfaz Isymunmanagedwriter4 (.</span><span class="sxs-lookup"><span data-stu-id="b4495-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4495-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4495-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="b4495-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b4495-105">Methods</span></span>  
 <span data-ttu-id="b4495-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="b4495-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="b4495-107">Método</span><span class="sxs-lookup"><span data-stu-id="b4495-107">Method</span></span>|<span data-ttu-id="b4495-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4495-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4495-109">GetDebugInfoWithPadding (método)</span><span class="sxs-lookup"><span data-stu-id="b4495-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="b4495-110">Funciona igual que el [método GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , salvo que la cadena de ruta de acceso se rellena con ceros después del carácter nulo de terminación para convertir los datos de cadena en un tamaño fijo de `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="b4495-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="b4495-111">El relleno solo se proporciona si la longitud de la cadena de ruta de acceso es menor que `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="b4495-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="b4495-112">Esto facilita la escritura de herramientas que diferencian los archivos PE.</span><span class="sxs-lookup"><span data-stu-id="b4495-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4495-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4495-113">Requirements</span></span>  
 <span data-ttu-id="b4495-114">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b4495-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4495-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4495-115">See also</span></span>

- [<span data-ttu-id="b4495-116">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="b4495-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="b4495-117">ISymUnmanagedWriter3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4495-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
