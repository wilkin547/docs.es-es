---
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
ms.openlocfilehash: fef2652f591e713140c651a9cb0df1ea9e6236c8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005589"
---
# <a name="-filealign"></a><span data-ttu-id="91cce-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="91cce-102">-filealign</span></span>
<span data-ttu-id="91cce-103">Especifica dónde se alinean las secciones del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="91cce-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91cce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91cce-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="91cce-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="91cce-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="91cce-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="91cce-106">Required.</span></span> <span data-ttu-id="91cce-107">Un valor que especifica la alineación de las secciones del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="91cce-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="91cce-108">Los valores válidos son 512, 1024, 2048, 4096 y 8192.</span><span class="sxs-lookup"><span data-stu-id="91cce-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="91cce-109">Estos valores están en bytes.</span><span class="sxs-lookup"><span data-stu-id="91cce-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91cce-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91cce-110">Remarks</span></span>  
 <span data-ttu-id="91cce-111">Puede usar la opción `-filealign` para especificar la alineación de las secciones en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="91cce-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="91cce-112">Las secciones son bloques de memoria contigua en un archivo portable ejecutable (PE) que contiene código o datos.</span><span class="sxs-lookup"><span data-stu-id="91cce-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="91cce-113">La opción `-filealign` permite compilar la aplicación con una alineación no estándar; la mayoría de los desarrolladores no necesitan usar esta opción.</span><span class="sxs-lookup"><span data-stu-id="91cce-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="91cce-114">Cada sección se alinea en un límite que es un múltiplo del valor `-filealign`.</span><span class="sxs-lookup"><span data-stu-id="91cce-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="91cce-115">No hay ningún valor predeterminado fijo.</span><span class="sxs-lookup"><span data-stu-id="91cce-115">There is no fixed default.</span></span> <span data-ttu-id="91cce-116">Si no se especifica `-filealign`, el compilador elige un valor predeterminado en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="91cce-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="91cce-117">Al especificar el tamaño de la sección, puede cambiar el tamaño del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="91cce-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="91cce-118">Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="91cce-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91cce-119">La opción `-filealign` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="91cce-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91cce-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="91cce-120">See also</span></span>

- [<span data-ttu-id="91cce-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="91cce-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
