---
title: '#pragma checksum (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0604a559be25c300fcdc6041975306b465fc595f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="76e62-102">#pragma checksum (Referencia del programador de C#)</span><span class="sxs-lookup"><span data-stu-id="76e62-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="76e62-103">Genera las sumas de comprobación para archivos de código fuente para ayudar en la depuración de páginas [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76e62-103">Generates checksums for source files to aid with debugging [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e62-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76e62-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76e62-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76e62-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="76e62-106">El nombre del archivo que requiere la supervisión para cambios o actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="76e62-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="76e62-107">El identificador único global (GUID) del archivo.</span><span class="sxs-lookup"><span data-stu-id="76e62-107">The Globally Unique Identifier (GUID) for the file.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="76e62-108">La cadena de dígitos hexadecimales que representa los bytes de la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="76e62-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="76e62-109">Debe ser un número par de dígitos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="76e62-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="76e62-110">Un número impar de dígitos produce una advertencia de tiempo de compilación y la directiva se ignora.</span><span class="sxs-lookup"><span data-stu-id="76e62-110">An odd number of digits results in a compile-time warning, and the directive are  ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76e62-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76e62-111">Remarks</span></span>  
 <span data-ttu-id="76e62-112">El depurador de Visual Studio usa una suma de comprobación para asegurarse de que siempre encuentra el código fuente correcto.</span><span class="sxs-lookup"><span data-stu-id="76e62-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="76e62-113">El compilador calcula la suma de comprobación para un archivo de origen y, después, emite el resultado en el archivo de base de datos del programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="76e62-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="76e62-114">Después, el depurador usa el archivo PDB para comparar la suma de comprobación que calcula para el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="76e62-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="76e62-115">Esta solución no funciona para proyectos de [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)], ya que la suma de comprobación calculada es para el archivo de código fuente generado, no para el archivo .aspx.</span><span class="sxs-lookup"><span data-stu-id="76e62-115">This solution does not work for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="76e62-116">Para solucionar este problema, `#pragma checksum` proporciona compatibilidad con la suma de comprobación para páginas [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="76e62-116">To address this problem, `#pragma checksum` provides checksum support for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
 <span data-ttu-id="76e62-117">Cuando se crea un proyecto de [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] en [!INCLUDE[csprcs](~/includes/csprcs-md.md)], el archivo de código fuente generado contiene una suma de comprobación para el archivo .aspx, desde el que se genera el código fuente.</span><span class="sxs-lookup"><span data-stu-id="76e62-117">When you create an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] project in [!INCLUDE[csprcs](~/includes/csprcs-md.md)], the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="76e62-118">Después, el compilador escribe esta información en el archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="76e62-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="76e62-119">Si el compilador no encuentra ninguna directiva `#pragma checksum` en el archivo, calcula la suma de comprobación y escribe el valor en el archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="76e62-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76e62-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76e62-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="76e62-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="76e62-121">See Also</span></span>  
 [<span data-ttu-id="76e62-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="76e62-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="76e62-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="76e62-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="76e62-124">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="76e62-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
