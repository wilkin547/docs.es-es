---
title: /codepage (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 609373ed0e58eec86a703f33d48d31e27b0b7e3c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="codepage-visual-basic"></a><span data-ttu-id="b0bbc-102">/codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0bbc-102">/codepage (Visual Basic)</span></span>
<span data-ttu-id="b0bbc-103">Especifica la página de códigos que se va a utilizar para todos los archivos de código fuente en la compilación.</span><span class="sxs-lookup"><span data-stu-id="b0bbc-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0bbc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0bbc-104">Syntax</span></span>  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="b0bbc-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b0bbc-105">Arguments</span></span>  
  
|<span data-ttu-id="b0bbc-106">Término</span><span class="sxs-lookup"><span data-stu-id="b0bbc-106">Term</span></span>|<span data-ttu-id="b0bbc-107">Definición</span><span class="sxs-lookup"><span data-stu-id="b0bbc-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="b0bbc-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="b0bbc-108">Required.</span></span> <span data-ttu-id="b0bbc-109">El compilador utiliza la página de códigos especificada por `id` para interpretar la codificación de los archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="b0bbc-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0bbc-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0bbc-110">Remarks</span></span>  
 <span data-ttu-id="b0bbc-111">Para compilar código fuente guardado con una codificación específica, puede usar `/codepage` para especificar la página de códigos que debe utilizarse.</span><span class="sxs-lookup"><span data-stu-id="b0bbc-111">To compile source code saved with a specific encoding, you can use `/codepage` to specify which code page should be used.</span></span> <span data-ttu-id="b0bbc-112">El `/codepage` opción se aplica a todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="b0bbc-112">The `/codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="b0bbc-113">Para obtener más información, consulte [codificación de caracteres en .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span><span class="sxs-lookup"><span data-stu-id="b0bbc-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="b0bbc-114">El `/codepage` opción no es necesaria si los archivos de código fuente se guardaron utilizando la página de códigos ANSI actual, Unicode o UTF-8 con una firma.</span><span class="sxs-lookup"><span data-stu-id="b0bbc-114">The `/codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="b0bbc-115">guarda todos los archivos de código fuente con la página de códigos ANSI actual de forma predeterminada, a menos que el usuario especifique otra codificación en el **codificación** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b0bbc-115"> saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="b0bbc-116">usa el **codificación** cuadro de diálogo para abrir archivos de código fuente guardados con una página de códigos diferente.</span><span class="sxs-lookup"><span data-stu-id="b0bbc-116"> uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0bbc-117">El `/codepage` opción no está disponible en la [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] entorno de desarrollo; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="b0bbc-117">The `/codepage` option is not available from within the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0bbc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0bbc-118">See Also</span></span>  
 [<span data-ttu-id="b0bbc-119">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b0bbc-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
