---
title: GetTypeLibInfo (Función)
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ec28c581b8e6e0aff3a2765720b6e9795be931b
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "44756060"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="a1c4d-102">GetTypeLibInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="a1c4d-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="a1c4d-103">Devuelve información acerca de la biblioteca de tipos especificado examinando su [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) estructura.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c4d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1c4d-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1c4d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1c4d-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="a1c4d-106">[in] El nombre de la biblioteca de tipos de archivo.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="a1c4d-107">[out] El GUID de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="a1c4d-108">[out] El identificador de localización de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="a1c4d-109">[out] Un [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) marca que identifica el sistema operativo de destino para la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-109">[out] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="a1c4d-110">Los valores habituales son SYS_WIN32 y SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="a1c4d-111">[out] El número de versión principal de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="a1c4d-112">Por ejemplo, para la versión *x.y*, el número de versión principal es *x*.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="a1c4d-113">[out] El número de versión secundaria de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="a1c4d-114">Por ejemplo, para la versión *x.y*, el número de versión secundaria es *y*.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1c4d-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1c4d-115">Remarks</span></span>  
 <span data-ttu-id="a1c4d-116">El `GetTypeLibInfo` llama a la función el [Tlbexp.exe (exportador de biblioteca)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="a1c4d-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="a1c4d-117">Esta herramienta genera una biblioteca de tipos que se describe los tipos en un ensamblado de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a1c4d-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="a1c4d-118">Si cualquier parámetro es null, la función devuelve un `HRESULT` de `E_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="a1c4d-119">De lo contrario, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="a1c4d-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1c4d-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1c4d-120">Requirements</span></span>  
 <span data-ttu-id="a1c4d-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1c4d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1c4d-122">**Encabezado:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="a1c4d-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="a1c4d-123">**Biblioteca:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="a1c4d-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="a1c4d-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1c4d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c4d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1c4d-125">See Also</span></span>  
 [<span data-ttu-id="a1c4d-126">Funciones auxiliares Tlbexp</span><span class="sxs-lookup"><span data-stu-id="a1c4d-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [<span data-ttu-id="a1c4d-127">LoadTypeLibEx de la función</span><span class="sxs-lookup"><span data-stu-id="a1c4d-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
