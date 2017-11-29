---
title: "IMetaDataImport2::GetVersionString (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetVersionString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d08f43a790305c960d557064539de680a2d04af9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="d80bc-102">IMetaDataImport2::GetVersionString (Método)</span><span class="sxs-lookup"><span data-stu-id="d80bc-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="d80bc-103">Obtiene el número de versión del runtime que se usó para generar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d80bc-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d80bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d80bc-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d80bc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d80bc-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="d80bc-106">[out] Una matriz para almacenar la cadena que especifica la versión.</span><span class="sxs-lookup"><span data-stu-id="d80bc-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="d80bc-107">[in] El tamaño, en caracteres anchos, de la `pwzBuf` matriz.</span><span class="sxs-lookup"><span data-stu-id="d80bc-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="d80bc-108">[out] Devuelve el número de caracteres anchos, incluido un terminador nulo, en la `pwzBuf` matriz.</span><span class="sxs-lookup"><span data-stu-id="d80bc-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d80bc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d80bc-109">Remarks</span></span>  
 <span data-ttu-id="d80bc-110">El `GetVersionString` método obtiene la versión compilada para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="d80bc-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="d80bc-111">Si el ámbito nunca se ha guardado, no tendrá una versión compilada para y se devolverá una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="d80bc-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d80bc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d80bc-112">Requirements</span></span>  
 <span data-ttu-id="d80bc-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d80bc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d80bc-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d80bc-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d80bc-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d80bc-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d80bc-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d80bc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d80bc-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d80bc-117">See Also</span></span>  
 [<span data-ttu-id="d80bc-118">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d80bc-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="d80bc-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d80bc-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
