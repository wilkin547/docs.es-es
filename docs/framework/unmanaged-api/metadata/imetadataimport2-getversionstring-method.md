---
title: IMetaDataImport2::GetVersionString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 112ddcf51a5637bb89df9479850c2a4a70d2e1d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448731"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="fba3c-102">IMetaDataImport2::GetVersionString (Método)</span><span class="sxs-lookup"><span data-stu-id="fba3c-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="fba3c-103">Obtiene el número de versión del runtime que se usó para generar el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fba3c-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fba3c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fba3c-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fba3c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fba3c-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="fba3c-106">[out] Una matriz para almacenar la cadena que especifica la versión.</span><span class="sxs-lookup"><span data-stu-id="fba3c-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="fba3c-107">[in] El tamaño, en caracteres anchos, de la `pwzBuf` matriz.</span><span class="sxs-lookup"><span data-stu-id="fba3c-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="fba3c-108">[out] Devuelve el número de caracteres anchos, incluido un terminador nulo, en la `pwzBuf` matriz.</span><span class="sxs-lookup"><span data-stu-id="fba3c-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fba3c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fba3c-109">Remarks</span></span>  
 <span data-ttu-id="fba3c-110">El `GetVersionString` método obtiene la versión compilada para el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="fba3c-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="fba3c-111">Si el ámbito nunca se ha guardado, no tendrá una versión compilada para y se devolverá una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="fba3c-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fba3c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fba3c-112">Requirements</span></span>  
 <span data-ttu-id="fba3c-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fba3c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fba3c-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fba3c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fba3c-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fba3c-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fba3c-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fba3c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba3c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fba3c-117">See Also</span></span>  
 [<span data-ttu-id="fba3c-118">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fba3c-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="fba3c-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fba3c-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
