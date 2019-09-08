---
title: Constantes (Referencia de la API no administrada)
ms.date: 03/30/2017
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b91f2a749557f94a68f1929d649824719160d9ee
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786954"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="4c3b1-102">Constantes (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="4c3b1-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="4c3b1-103">En este tema se describen las constantes de tipo de lenguaje, proveedor de lenguaje y tipo de documento que se definen en CorSym. idl.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="4c3b1-104">Constantes de tipo de lenguaje</span><span class="sxs-lookup"><span data-stu-id="4c3b1-104">Language Type Constants</span></span>  
 <span data-ttu-id="4c3b1-105">En la tabla siguiente se muestran las constantes de tipo de lenguaje, que representan los GUID que identifican los lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="4c3b1-106">Símbolo</span><span class="sxs-lookup"><span data-stu-id="4c3b1-106">Symbol</span></span>|<span data-ttu-id="4c3b1-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4c3b1-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4c3b1-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="4c3b1-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="4c3b1-109">Indica el lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="4c3b1-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="4c3b1-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="4c3b1-111">Indica el C++ idioma.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="4c3b1-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="4c3b1-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="4c3b1-113">Indica el C# idioma.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="4c3b1-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="4c3b1-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="4c3b1-115">Indica el lenguaje básico.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="4c3b1-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="4c3b1-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="4c3b1-117">Indica el lenguaje Java.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="4c3b1-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="4c3b1-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="4c3b1-119">Indica el lenguaje COBOL.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="4c3b1-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="4c3b1-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="4c3b1-121">Indica el lenguaje Pascal.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="4c3b1-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="4c3b1-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="4c3b1-123">Indica el código de ensamblado del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="4c3b1-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="4c3b1-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="4c3b1-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="4c3b1-125">Indica el lenguaje JScript.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="4c3b1-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="4c3b1-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="4c3b1-127">Indica el lenguaje SMC.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="4c3b1-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="4c3b1-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="4c3b1-129">Indica el C++ idioma habilitado para el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="4c3b1-130">Constantes de proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="4c3b1-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="4c3b1-131">En la tabla siguiente se muestran las constantes de proveedor de lenguaje, que representan los GUID que identifican a los proveedores de lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="4c3b1-132">Símbolo</span><span class="sxs-lookup"><span data-stu-id="4c3b1-132">Symbol</span></span>|<span data-ttu-id="4c3b1-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4c3b1-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4c3b1-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="4c3b1-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="4c3b1-135">Indica Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="4c3b1-136">Constantes de tipo de documento</span><span class="sxs-lookup"><span data-stu-id="4c3b1-136">Document Type Constants</span></span>  
 <span data-ttu-id="4c3b1-137">En la tabla siguiente se muestran las constantes de tipo de documento, que representan los GUID que identifican los tipos de documento.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="4c3b1-138">Símbolo</span><span class="sxs-lookup"><span data-stu-id="4c3b1-138">Symbol</span></span>|<span data-ttu-id="4c3b1-139">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4c3b1-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4c3b1-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="4c3b1-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="4c3b1-141">Indica un documento de texto.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="4c3b1-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="4c3b1-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="4c3b1-143">Indica un documento que no es de texto.</span><span class="sxs-lookup"><span data-stu-id="4c3b1-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c3b1-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c3b1-144">See also</span></span>

- [<span data-ttu-id="4c3b1-145">Referencia de API no administrada</span><span class="sxs-lookup"><span data-stu-id="4c3b1-145">Unmanaged API Reference</span></span>](index.md)
