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
ms.openlocfilehash: 8c76db644ffee478003d834460c155c4ec6d0070
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133957"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="949f3-102">Constantes (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="949f3-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="949f3-103">Este tema describe el tipo de lenguaje, proveedor de lenguaje y las constantes de tipo de documento que se definen en CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="949f3-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="949f3-104">Constantes de tipo de lenguaje</span><span class="sxs-lookup"><span data-stu-id="949f3-104">Language Type Constants</span></span>  
 <span data-ttu-id="949f3-105">La siguiente tabla muestra las constantes de tipo, que representan los identificadores GUID que identifican los lenguajes de programación de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="949f3-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="949f3-106">Símbolo</span><span class="sxs-lookup"><span data-stu-id="949f3-106">Symbol</span></span>|<span data-ttu-id="949f3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="949f3-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="949f3-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="949f3-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="949f3-109">Indica el lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="949f3-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="949f3-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="949f3-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="949f3-111">Indica el lenguaje C++.</span><span class="sxs-lookup"><span data-stu-id="949f3-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="949f3-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="949f3-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="949f3-113">Indica el C# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="949f3-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="949f3-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="949f3-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="949f3-115">Indica el idioma básico.</span><span class="sxs-lookup"><span data-stu-id="949f3-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="949f3-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="949f3-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="949f3-117">Indica el idioma de Java.</span><span class="sxs-lookup"><span data-stu-id="949f3-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="949f3-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="949f3-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="949f3-119">Indica el lenguaje COBOL.</span><span class="sxs-lookup"><span data-stu-id="949f3-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="949f3-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="949f3-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="949f3-121">Indica el lenguaje Pascal.</span><span class="sxs-lookup"><span data-stu-id="949f3-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="949f3-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="949f3-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="949f3-123">Indica el código de ensamblado de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="949f3-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="949f3-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="949f3-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="949f3-125">Indica el lenguaje JScript.</span><span class="sxs-lookup"><span data-stu-id="949f3-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="949f3-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="949f3-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="949f3-127">Indica el lenguaje SMC.</span><span class="sxs-lookup"><span data-stu-id="949f3-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="949f3-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="949f3-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="949f3-129">Indica el lenguaje C++ habilitado para .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="949f3-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="949f3-130">Constantes del proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="949f3-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="949f3-131">La siguiente tabla muestra constantes de proveedor, que representan los identificadores GUID que identifican los proveedores de lenguaje de programación de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="949f3-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="949f3-132">Símbolo</span><span class="sxs-lookup"><span data-stu-id="949f3-132">Symbol</span></span>|<span data-ttu-id="949f3-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="949f3-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="949f3-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="949f3-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="949f3-135">Indica a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="949f3-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="949f3-136">Constantes de tipo de documento</span><span class="sxs-lookup"><span data-stu-id="949f3-136">Document Type Constants</span></span>  
 <span data-ttu-id="949f3-137">La siguiente tabla muestra las constantes de tipo, que representan los identificadores GUID que identifican los tipos de documento de documento.</span><span class="sxs-lookup"><span data-stu-id="949f3-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="949f3-138">Símbolo</span><span class="sxs-lookup"><span data-stu-id="949f3-138">Symbol</span></span>|<span data-ttu-id="949f3-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="949f3-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="949f3-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="949f3-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="949f3-141">Indica un documento de texto.</span><span class="sxs-lookup"><span data-stu-id="949f3-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="949f3-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="949f3-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="949f3-143">Indica un documento que no sean de texto.</span><span class="sxs-lookup"><span data-stu-id="949f3-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="949f3-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="949f3-144">See also</span></span>

- [<span data-ttu-id="949f3-145">Referencia de la API no administrada</span><span class="sxs-lookup"><span data-stu-id="949f3-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
