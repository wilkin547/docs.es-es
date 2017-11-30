---
title: Constantes (Referencia de la API no administrada)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45e4d41c16695010dc452d2f22850d43f885974a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="8d6ac-102">Constantes (Referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="8d6ac-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="8d6ac-103">Este tema describe el tipo de lenguaje, proveedor de lenguaje y constantes de tipo de documento que se definen en CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="8d6ac-104">Constantes de tipo de lenguaje</span><span class="sxs-lookup"><span data-stu-id="8d6ac-104">Language Type Constants</span></span>  
 <span data-ttu-id="8d6ac-105">La siguiente tabla muestra las constantes de tipo, que representan GUID que identifican los lenguajes de programación de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="8d6ac-106">Símbolo</span><span class="sxs-lookup"><span data-stu-id="8d6ac-106">Symbol</span></span>|<span data-ttu-id="8d6ac-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d6ac-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8d6ac-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="8d6ac-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="8d6ac-109">Indica el lenguaje C.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="8d6ac-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="8d6ac-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="8d6ac-111">Indica el lenguaje C++.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="8d6ac-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="8d6ac-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="8d6ac-113">Indica el lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="8d6ac-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="8d6ac-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="8d6ac-115">Indica el idioma básico.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="8d6ac-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="8d6ac-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="8d6ac-117">Indica el idioma de Java.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="8d6ac-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="8d6ac-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="8d6ac-119">Indica el lenguaje COBOL.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="8d6ac-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="8d6ac-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="8d6ac-121">Indica el lenguaje Pascal.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="8d6ac-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="8d6ac-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="8d6ac-123">Indica el código de ensamblado de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="8d6ac-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="8d6ac-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="8d6ac-125">Indica el lenguaje JScript.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="8d6ac-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="8d6ac-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="8d6ac-127">Indica el lenguaje de SMC.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="8d6ac-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="8d6ac-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="8d6ac-129">Indica el lenguaje C++ habilitado para .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="8d6ac-130">Constantes del proveedor de lenguaje</span><span class="sxs-lookup"><span data-stu-id="8d6ac-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="8d6ac-131">En la tabla siguiente muestra constantes de proveedor, que representan GUID que identifican los proveedores de lenguaje de programación de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="8d6ac-132">Símbolo</span><span class="sxs-lookup"><span data-stu-id="8d6ac-132">Symbol</span></span>|<span data-ttu-id="8d6ac-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d6ac-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8d6ac-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d6ac-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="8d6ac-135">Indica que Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="8d6ac-136">Constantes de tipo de documento</span><span class="sxs-lookup"><span data-stu-id="8d6ac-136">Document Type Constants</span></span>  
 <span data-ttu-id="8d6ac-137">La siguiente tabla muestra las constantes de tipo, que representan GUID que identifican los tipos de documento de documento.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="8d6ac-138">Símbolo</span><span class="sxs-lookup"><span data-stu-id="8d6ac-138">Symbol</span></span>|<span data-ttu-id="8d6ac-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d6ac-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8d6ac-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="8d6ac-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="8d6ac-141">Indica un documento de texto.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="8d6ac-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="8d6ac-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="8d6ac-143">Indica un documento no son de texto.</span><span class="sxs-lookup"><span data-stu-id="8d6ac-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d6ac-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d6ac-144">See Also</span></span>  
 [<span data-ttu-id="8d6ac-145">Referencia de API no administrada</span><span class="sxs-lookup"><span data-stu-id="8d6ac-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
