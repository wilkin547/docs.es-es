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
ms.openlocfilehash: e64a0512e05965b3da2e7486e986ee34ca8a20d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104301"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="c5d01-102">GetTypeLibInfo (Función)</span><span class="sxs-lookup"><span data-stu-id="c5d01-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="c5d01-103">Devuelve información sobre la biblioteca de tipos especificada examinando su estructura [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) .</span><span class="sxs-lookup"><span data-stu-id="c5d01-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5d01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5d01-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c5d01-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5d01-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="c5d01-106">de Nombre de archivo de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c5d01-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="c5d01-107">enuncia GUID de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c5d01-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="c5d01-108">enuncia IDENTIFICADOR de localización de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c5d01-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="c5d01-109">enuncia Marca [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el sistema operativo de destino de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c5d01-109">[out] A [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="c5d01-110">Los valores comunes son SYS_WIN32 y SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="c5d01-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="c5d01-111">enuncia Número de versión principal de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c5d01-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="c5d01-112">Por ejemplo, para la versión *x. y*, el número de versión principal es *x*.</span><span class="sxs-lookup"><span data-stu-id="c5d01-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="c5d01-113">enuncia Número de versión secundaria de la biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="c5d01-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="c5d01-114">Por ejemplo, para la versión *x. y*, el número de versión secundaria es *y*.</span><span class="sxs-lookup"><span data-stu-id="c5d01-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5d01-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5d01-115">Remarks</span></span>  
 <span data-ttu-id="c5d01-116">La función `GetTypeLibInfo` se llama mediante el método [Tlbexp. exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="c5d01-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="c5d01-117">Esta herramienta genera una biblioteca de tipos que describe los tipos de un ensamblado de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c5d01-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="c5d01-118">Si un parámetro es null, la función devuelve un `HRESULT` de `E_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="c5d01-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="c5d01-119">De lo contrario, devuelve `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="c5d01-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5d01-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5d01-120">Requirements</span></span>  
 <span data-ttu-id="c5d01-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5d01-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5d01-122">**Encabezado:** TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="c5d01-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="c5d01-123">**Biblioteca:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="c5d01-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="c5d01-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5d01-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5d01-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5d01-125">See also</span></span>

- [<span data-ttu-id="c5d01-126">Funciones del asistente Tlbexp</span><span class="sxs-lookup"><span data-stu-id="c5d01-126">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="c5d01-127">LoadTypeLibEx función)</span><span class="sxs-lookup"><span data-stu-id="c5d01-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
