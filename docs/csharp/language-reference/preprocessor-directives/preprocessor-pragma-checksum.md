---
title: '#pragma checksum: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 1bbb404e1183daa5e68e512e7439b6ae52abd605
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712486"
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="a97be-102">#pragma checksum (Referencia del programador de C#)</span><span class="sxs-lookup"><span data-stu-id="a97be-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="a97be-103">Genera sumas de comprobación de archivos de código fuente para ayudar con la depuración de páginas ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a97be-103">Generates checksums for source files to aid with debugging ASP.NET pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a97be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a97be-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
## <a name="parameters"></a><span data-ttu-id="a97be-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a97be-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="a97be-106">El nombre del archivo que requiere la supervisión para cambios o actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a97be-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="a97be-107">El identificador único global (GUID) del algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="a97be-107">The Globally Unique Identifier (GUID) for the hash algorithm.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="a97be-108">La cadena de dígitos hexadecimales que representa los bytes de la suma de comprobación.</span><span class="sxs-lookup"><span data-stu-id="a97be-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="a97be-109">Debe ser un número par de dígitos hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="a97be-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="a97be-110">Un número impar de dígitos genera una advertencia de tiempo de compilación y la directiva se ignora.</span><span class="sxs-lookup"><span data-stu-id="a97be-110">An odd number of digits results in a compile-time warning, and the directive are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a97be-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a97be-111">Remarks</span></span>  
 <span data-ttu-id="a97be-112">El depurador de Visual Studio usa una suma de comprobación para asegurarse de que siempre encuentra el código fuente correcto.</span><span class="sxs-lookup"><span data-stu-id="a97be-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="a97be-113">El compilador calcula la suma de comprobación para un archivo de origen y, después, emite el resultado en el archivo de base de datos del programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="a97be-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="a97be-114">Después, el depurador usa el archivo PDB para comparar la suma de comprobación que calcula para el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="a97be-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="a97be-115">Esta solución no funciona para proyectos de ASP.NET, ya que la suma de comprobación calculada es para el archivo de código fuente generado, no para el archivo .aspx.</span><span class="sxs-lookup"><span data-stu-id="a97be-115">This solution does not work for ASP.NET projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="a97be-116">Para solucionar este problema, `#pragma checksum` proporciona compatibilidad de la suma de comprobación con páginas ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a97be-116">To address this problem, `#pragma checksum` provides checksum support for ASP.NET pages.</span></span>  
  
 <span data-ttu-id="a97be-117">Cuando se crea un proyecto de ASP.NET en Visual C#, el archivo de código fuente generado contiene una suma de comprobación del archivo .aspx desde el que se genera el código fuente.</span><span class="sxs-lookup"><span data-stu-id="a97be-117">When you create an ASP.NET project in Visual C#, the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="a97be-118">Después, el compilador escribe esta información en el archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="a97be-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="a97be-119">Si el compilador no encuentra ninguna directiva `#pragma checksum` en el archivo, calcula la suma de comprobación y escribe el valor en el archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="a97be-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a97be-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a97be-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a97be-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a97be-121">See also</span></span>

- [<span data-ttu-id="a97be-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a97be-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a97be-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a97be-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a97be-124">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="a97be-124">C# Preprocessor Directives</span></span>](./index.md)
