---
description: 'Más información acerca de: GetTypeLibInfo ((función)'
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
ms.openlocfilehash: 61a830f3ce81345634da377f6fc815a307700e9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794473"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="c7435-103">GetTypeLibInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="c7435-103">GetTypeLibInfo Function</span></span>

<span data-ttu-id="c7435-104">Devuelve información sobre la biblioteca de tipos especificada examinando su estructura [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) .</span><span class="sxs-lookup"><span data-stu-id="c7435-104">Returns information about the specified type library by examining its [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7435-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7435-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7435-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c7435-106">Parameters</span></span>  

 `szFile`  
 <span data-ttu-id="c7435-107">de Nombre de archivo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c7435-107">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="c7435-108">enuncia GUID de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c7435-108">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="c7435-109">enuncia IDENTIFICADOR de localización de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c7435-109">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="c7435-110">enuncia Marca [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el sistema operativo de destino de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c7435-110">[out] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="c7435-111">Los valores comunes son SYS_WIN32 y SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="c7435-111">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="c7435-112">enuncia Número de versión principal de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c7435-112">[out] The major version number of the type library.</span></span> <span data-ttu-id="c7435-113">Por ejemplo, para la versión *x. y*, el número de versión principal es *x*.</span><span class="sxs-lookup"><span data-stu-id="c7435-113">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="c7435-114">enuncia Número de versión secundaria de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c7435-114">[out] The minor version number of the type library.</span></span> <span data-ttu-id="c7435-115">Por ejemplo, para la versión *x. y*, el número de versión secundaria es *y*.</span><span class="sxs-lookup"><span data-stu-id="c7435-115">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7435-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c7435-116">Remarks</span></span>  

 <span data-ttu-id="c7435-117">El `GetTypeLibInfo` [Tlbexp.exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md)llama a la función.</span><span class="sxs-lookup"><span data-stu-id="c7435-117">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="c7435-118">Esta herramienta genera una biblioteca de tipos que describe los tipos de un ensamblado de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c7435-118">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="c7435-119">Si un parámetro es null, la función devuelve un `HRESULT` de `E_POINTER` .</span><span class="sxs-lookup"><span data-stu-id="c7435-119">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="c7435-120">En caso contrario, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="c7435-120">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7435-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c7435-121">Requirements</span></span>  

 <span data-ttu-id="c7435-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7435-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7435-123">**Encabezado:** TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="c7435-123">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="c7435-124">**Biblioteca:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="c7435-124">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="c7435-125">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7435-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7435-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7435-126">See also</span></span>

- [<span data-ttu-id="c7435-127">Funciones del asistente Tlbexp</span><span class="sxs-lookup"><span data-stu-id="c7435-127">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="c7435-128">LoadTypeLibEx función)</span><span class="sxs-lookup"><span data-stu-id="c7435-128">LoadTypeLibEx Function</span></span>](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
