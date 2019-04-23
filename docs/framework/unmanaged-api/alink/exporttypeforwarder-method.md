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
ms.openlocfilehash: 5bdf9fb50fe06141df6f3818c784588b9e2138af
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212029"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="7fd82-102">ExportTypeForwarder (Método)</span><span class="sxs-lookup"><span data-stu-id="7fd82-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="7fd82-103">Agrega un reenviador de tipos a la tabla de tipos del ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="7fd82-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fd82-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fd82-104">Syntax</span></span>  
  
```  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fd82-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7fd82-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="7fd82-106">Referencia al ensamblado al que hace referencia el reenviador de tipos.</span><span class="sxs-lookup"><span data-stu-id="7fd82-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="7fd82-107">Nombre de tipo completo para exportar.</span><span class="sxs-lookup"><span data-stu-id="7fd82-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7fd82-108">`ComType` marca como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="7fd82-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="7fd82-109">Este valor puede pasarse a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="7fd82-109">This value may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="7fd82-110">Recibe el token del tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="7fd82-110">Receives the token of the exported type.</span></span> <span data-ttu-id="7fd82-111">Esto sólo es necesario para emitir tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="7fd82-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7fd82-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7fd82-112">Return Value</span></span>  
 <span data-ttu-id="7fd82-113">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="7fd82-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fd82-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7fd82-114">Requirements</span></span>  
 <span data-ttu-id="7fd82-115">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="7fd82-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd82-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fd82-116">See also</span></span>

- [<span data-ttu-id="7fd82-117">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7fd82-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="7fd82-118">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7fd82-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="7fd82-119">API de ALink</span><span class="sxs-lookup"><span data-stu-id="7fd82-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
