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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f97f46595f43c7576c499c6b9944f7e3509662fb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742011"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="45a58-102">ExportTypeForwarder (Método)</span><span class="sxs-lookup"><span data-stu-id="45a58-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="45a58-103">Agrega un reenviador de tipos a la tabla de tipos del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="45a58-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a58-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45a58-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="45a58-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45a58-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="45a58-106">Referencia al ensamblado al que hace referencia el reenviador de tipos.</span><span class="sxs-lookup"><span data-stu-id="45a58-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="45a58-107">Nombre de tipo completo para exportar.</span><span class="sxs-lookup"><span data-stu-id="45a58-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="45a58-108">`ComType` marca como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="45a58-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="45a58-109">Este valor puede pasarse a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="45a58-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="45a58-110">Recibe el token del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="45a58-110">Receives the token of the exported type.</span></span> <span data-ttu-id="45a58-111">Esto sólo es necesario para emitir tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="45a58-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45a58-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="45a58-112">Return Value</span></span>  
 <span data-ttu-id="45a58-113">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="45a58-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45a58-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45a58-114">Requirements</span></span>  
 <span data-ttu-id="45a58-115">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="45a58-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a58-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="45a58-116">See also</span></span>

- [<span data-ttu-id="45a58-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45a58-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="45a58-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45a58-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="45a58-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="45a58-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
