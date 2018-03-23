---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 736b35f51657aa7b21a6a077d70f5e9ff0d4fb85
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="fdf44-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdf44-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="fdf44-103">Especifica la página de códigos que se va a utilizar para todos los archivos de código fuente en la compilación.</span><span class="sxs-lookup"><span data-stu-id="fdf44-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdf44-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdf44-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="fdf44-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fdf44-105">Arguments</span></span>  
  
|<span data-ttu-id="fdf44-106">Término</span><span class="sxs-lookup"><span data-stu-id="fdf44-106">Term</span></span>|<span data-ttu-id="fdf44-107">Definición</span><span class="sxs-lookup"><span data-stu-id="fdf44-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="fdf44-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="fdf44-108">Required.</span></span> <span data-ttu-id="fdf44-109">El compilador utiliza la página de códigos especificada por `id` para interpretar la codificación de los archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="fdf44-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdf44-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fdf44-110">Remarks</span></span>  
 <span data-ttu-id="fdf44-111">Para compilar código fuente guardado con una codificación específica, puede usar `-codepage` para especificar la página de códigos que debe utilizarse.</span><span class="sxs-lookup"><span data-stu-id="fdf44-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="fdf44-112">El `-codepage` opción se aplica a todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="fdf44-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="fdf44-113">Para obtener más información, consulte [codificación de caracteres en .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span><span class="sxs-lookup"><span data-stu-id="fdf44-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="fdf44-114">El `-codepage` opción no es necesaria si los archivos de código fuente se guardaron utilizando la página de códigos ANSI actual, Unicode o UTF-8 con una firma.</span><span class="sxs-lookup"><span data-stu-id="fdf44-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="fdf44-115"> guarda todos los archivos de código fuente con la página de códigos ANSI actual de forma predeterminada, a menos que el usuario especifique otra codificación en el **codificación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="fdf44-115"> saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="fdf44-116"> usa el **codificación** cuadro de diálogo para abrir archivos de código fuente guardados con una página de códigos diferente.</span><span class="sxs-lookup"><span data-stu-id="fdf44-116"> uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fdf44-117">El `-codepage` opción no está disponible en la [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] entorno de desarrollo; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="fdf44-117">The `-codepage` option is not available from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdf44-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdf44-118">See Also</span></span>  
 [<span data-ttu-id="fdf44-119">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fdf44-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
