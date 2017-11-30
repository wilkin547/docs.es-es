---
title: "ExportType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ExportType
api_location: alink.dll
api_type: COM
f1_keywords: ExportType
helpviewer_keywords: ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3f7bd3991fa57f11674b7ef0b9b62d12376fa765
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="exporttype-method"></a><span data-ttu-id="f2f61-102">ExportType (Método)</span><span class="sxs-lookup"><span data-stu-id="f2f61-102">ExportType Method</span></span>
<span data-ttu-id="f2f61-103">Especifica que un tipo es exportable.</span><span class="sxs-lookup"><span data-stu-id="f2f61-103">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f61-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2f61-104">Syntax</span></span>  
  
```  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2f61-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2f61-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f2f61-106">Id. del ensamblado que se va a exportar desde.</span><span class="sxs-lookup"><span data-stu-id="f2f61-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f2f61-107">Símbolo (token) o ensamblado identificador del archivo que define el tipo exportable.</span><span class="sxs-lookup"><span data-stu-id="f2f61-107">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="f2f61-108">Símbolo (token) de tipo hacer exportable.</span><span class="sxs-lookup"><span data-stu-id="f2f61-108">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="f2f61-109">Nombre de tipo completo hacer exportable.</span><span class="sxs-lookup"><span data-stu-id="f2f61-109">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f2f61-110">`ComType`marca como `tdPublic` o `tdNested`.</span><span class="sxs-lookup"><span data-stu-id="f2f61-110">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="f2f61-111">Este parámetro se puede pasar a [DefineExportedType (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="f2f61-111">This parameter may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="f2f61-112">Recibe el token de tipos exportada.</span><span class="sxs-lookup"><span data-stu-id="f2f61-112">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2f61-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f2f61-113">Return Value</span></span>  
 <span data-ttu-id="f2f61-114">Devuelve S_OK si el método tiene éxito.</span><span class="sxs-lookup"><span data-stu-id="f2f61-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2f61-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2f61-115">Requirements</span></span>  
 <span data-ttu-id="f2f61-116">Requiere alink.h</span><span class="sxs-lookup"><span data-stu-id="f2f61-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f61-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2f61-117">See Also</span></span>  
 [<span data-ttu-id="f2f61-118">IALink (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2f61-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f2f61-119">IALink2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2f61-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f2f61-120">API de ALink</span><span class="sxs-lookup"><span data-stu-id="f2f61-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
