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
ms.openlocfilehash: 809b7ad005b6bb5f127f84425b5d2beb980df471
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058136"
---
# <a name="-filealign"></a><span data-ttu-id="0cc2a-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="0cc2a-102">-filealign</span></span>

<span data-ttu-id="0cc2a-103">Especifica dónde se alinean las secciones del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cc2a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cc2a-104">Syntax</span></span>  
  
```console  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="0cc2a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0cc2a-105">Arguments</span></span>  

 `number`  
 <span data-ttu-id="0cc2a-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-106">Required.</span></span> <span data-ttu-id="0cc2a-107">Un valor que especifica la alineación de las secciones del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="0cc2a-108">Los valores válidos son 512, 1024, 2048, 4096 y 8192.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="0cc2a-109">Estos valores están en bytes.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cc2a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0cc2a-110">Remarks</span></span>  

 <span data-ttu-id="0cc2a-111">Puede usar la opción `-filealign` para especificar la alineación de las secciones en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="0cc2a-112">Las secciones son bloques de memoria contigua en un archivo portable ejecutable (PE) que contiene código o datos.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="0cc2a-113">La opción `-filealign` permite compilar la aplicación con una alineación no estándar; la mayoría de los desarrolladores no necesitan usar esta opción.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="0cc2a-114">Cada sección se alinea en un límite que es un múltiplo del valor `-filealign`.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="0cc2a-115">No hay ningún valor predeterminado fijo.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-115">There is no fixed default.</span></span> <span data-ttu-id="0cc2a-116">Si no se especifica `-filealign`, el compilador elige un valor predeterminado en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="0cc2a-117">Al especificar el tamaño de la sección, puede cambiar el tamaño del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="0cc2a-118">Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cc2a-119">La opción `-filealign` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0cc2a-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc2a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cc2a-120">See also</span></span>

- [<span data-ttu-id="0cc2a-121">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0cc2a-121">Visual Basic Command-Line Compiler</span></span>](index.md)
