---
description: Más información sobre -filealign
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: f32ae370c0ef832b501f085351eadb9b6156c730
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100470296"
---
# <a name="-filealign"></a><span data-ttu-id="c82d5-103">-filealign</span><span class="sxs-lookup"><span data-stu-id="c82d5-103">-filealign</span></span>

<span data-ttu-id="c82d5-104">Especifica dónde se alinean las secciones del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="c82d5-104">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c82d5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c82d5-105">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="c82d5-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c82d5-106">Arguments</span></span>  

 `number`  
 <span data-ttu-id="c82d5-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c82d5-107">Required.</span></span> <span data-ttu-id="c82d5-108">Un valor que especifica la alineación de las secciones del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="c82d5-108">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="c82d5-109">Los valores válidos son 512, 1024, 2048, 4096 y 8192.</span><span class="sxs-lookup"><span data-stu-id="c82d5-109">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="c82d5-110">Estos valores están en bytes.</span><span class="sxs-lookup"><span data-stu-id="c82d5-110">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c82d5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c82d5-111">Remarks</span></span>  

 <span data-ttu-id="c82d5-112">Puede usar la opción `-filealign` para especificar la alineación de las secciones en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="c82d5-112">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="c82d5-113">Las secciones son bloques de memoria contigua en un archivo portable ejecutable (PE) que contiene código o datos.</span><span class="sxs-lookup"><span data-stu-id="c82d5-113">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="c82d5-114">La opción `-filealign` permite compilar la aplicación con una alineación no estándar; la mayoría de los desarrolladores no necesitan usar esta opción.</span><span class="sxs-lookup"><span data-stu-id="c82d5-114">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="c82d5-115">Cada sección se alinea en un límite que es un múltiplo del valor `-filealign`.</span><span class="sxs-lookup"><span data-stu-id="c82d5-115">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="c82d5-116">No hay ningún valor predeterminado fijo.</span><span class="sxs-lookup"><span data-stu-id="c82d5-116">There is no fixed default.</span></span> <span data-ttu-id="c82d5-117">Si no se especifica `-filealign`, el compilador elige un valor predeterminado en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="c82d5-117">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="c82d5-118">Al especificar el tamaño de la sección, puede cambiar el tamaño del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="c82d5-118">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="c82d5-119">Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="c82d5-119">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c82d5-120">La opción `-filealign` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c82d5-120">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c82d5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c82d5-121">See also</span></span>

- [<span data-ttu-id="c82d5-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c82d5-122">Visual Basic Command-Line Compiler</span></span>](index.md)
