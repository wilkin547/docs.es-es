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
ms.openlocfilehash: 56a9b97f37240e385dbd1788bafea62578d687a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457873"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="51e0f-102">GetTypeLibInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="51e0f-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="51e0f-103">Devuelve información acerca de la biblioteca de tipos especificada mediante el examen de su [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) estructura.</span><span class="sxs-lookup"><span data-stu-id="51e0f-103">Returns information about the specified type library by examining its [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51e0f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51e0f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="51e0f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51e0f-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="51e0f-106">[in] El nombre de archivo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="51e0f-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="51e0f-107">[out] El GUID de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="51e0f-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="51e0f-108">[out] Identificador de localización de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="51e0f-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="51e0f-109">[out] A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) marca que identifica el sistema operativo de destino para la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="51e0f-109">[out] A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="51e0f-110">Los valores habituales son SYS_WIN32 y SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="51e0f-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="51e0f-111">[out] El número de versión principal de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="51e0f-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="51e0f-112">Por ejemplo, para la versión *x.y*, el número de versión principal es *x*.</span><span class="sxs-lookup"><span data-stu-id="51e0f-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="51e0f-113">[out] El número de versión secundaria de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="51e0f-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="51e0f-114">Por ejemplo, para la versión *x.y*, el número de versión secundaria es *y*.</span><span class="sxs-lookup"><span data-stu-id="51e0f-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51e0f-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51e0f-115">Remarks</span></span>  
 <span data-ttu-id="51e0f-116">El `GetTypeLibInfo` función llama a la [Tlbexp.exe (exportador de la biblioteca de tipos)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="51e0f-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="51e0f-117">Esta herramienta genera una biblioteca de tipos que describe los tipos en un ensamblado de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="51e0f-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="51e0f-118">Si cualquier parámetro es null, la función devuelve un `HRESULT` de `E_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="51e0f-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="51e0f-119">De lo contrario, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="51e0f-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51e0f-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51e0f-120">Requirements</span></span>  
 <span data-ttu-id="51e0f-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51e0f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51e0f-122">**Encabezado:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="51e0f-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="51e0f-123">**Biblioteca:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="51e0f-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="51e0f-124">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51e0f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e0f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="51e0f-125">See Also</span></span>  
 [<span data-ttu-id="51e0f-126">Funciones auxiliares Tlbexp</span><span class="sxs-lookup"><span data-stu-id="51e0f-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="51e0f-127">[Función LoadTypeLibEx de la](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)</span><span class="sxs-lookup"><span data-stu-id="51e0f-127">[LoadTypeLibEx Function](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)</span></span>
