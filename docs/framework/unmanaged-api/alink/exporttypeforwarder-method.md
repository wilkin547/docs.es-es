---
title: ExportTypeForwarder (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
ms.openlocfilehash: 4e6ceabf37056bfc25247266be2c7801cb0e13e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684777"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="5a050-102">ExportTypeForwarder (Método)</span><span class="sxs-lookup"><span data-stu-id="5a050-102">ExportTypeForwarder Method</span></span>

<span data-ttu-id="5a050-103">Agrega un reenviador de tipos a la tabla de tipos del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="5a050-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a050-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a050-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a050-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a050-105">Parameters</span></span>  

 `tkAssemblyRef`  
 <span data-ttu-id="5a050-106">Referencia al ensamblado al que hace referencia el reenviador de tipos.</span><span class="sxs-lookup"><span data-stu-id="5a050-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="5a050-107">Nombre completo del tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="5a050-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5a050-108">`ComType` marcas como `tdPublic` o `tdNested` .</span><span class="sxs-lookup"><span data-stu-id="5a050-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="5a050-109">Este valor se puede pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="5a050-109">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="5a050-110">Recibe el token del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="5a050-110">Receives the token of the exported type.</span></span> <span data-ttu-id="5a050-111">Esto solo es necesario para emitir tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="5a050-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a050-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5a050-112">Return Value</span></span>  

 <span data-ttu-id="5a050-113">Devuelve S_OK si el método se ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a050-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a050-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a050-114">Requirements</span></span>  

 <span data-ttu-id="5a050-115">Requiere ALink. h</span><span class="sxs-lookup"><span data-stu-id="5a050-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a050-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a050-116">See also</span></span>

- [<span data-ttu-id="5a050-117">IALink (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a050-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5a050-118">IALink2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a050-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5a050-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="5a050-119">ALink API</span></span>](index.md)
