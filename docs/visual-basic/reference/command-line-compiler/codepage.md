---
description: Más información sobre -codepage (Visual Basic)
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: 8bc68263bda298787a48dc06729ea17c5adfcfa5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468283"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="e4a54-103">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4a54-103">-codepage (Visual Basic)</span></span>

<span data-ttu-id="e4a54-104">Especifica la página de códigos que se va a utilizar para todos los archivos de código fuente en la compilación.</span><span class="sxs-lookup"><span data-stu-id="e4a54-104">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4a54-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4a54-105">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="e4a54-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e4a54-106">Arguments</span></span>  
  
|<span data-ttu-id="e4a54-107">Término</span><span class="sxs-lookup"><span data-stu-id="e4a54-107">Term</span></span>|<span data-ttu-id="e4a54-108">Definición</span><span class="sxs-lookup"><span data-stu-id="e4a54-108">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="e4a54-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e4a54-109">Required.</span></span> <span data-ttu-id="e4a54-110">El compilador usa la página de códigos especificada por `id` para interpretar la codificación de los archivos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="e4a54-110">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4a54-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4a54-111">Remarks</span></span>  

 <span data-ttu-id="e4a54-112">Para compilar el código fuente guardado con una codificación específica, puede usar `-codepage` para especificar qué página de códigos debe usarse.</span><span class="sxs-lookup"><span data-stu-id="e4a54-112">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="e4a54-113">La opción `-codepage` se aplica a todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="e4a54-113">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="e4a54-114">Para más información, consulte [Codificación de caracteres en .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="e4a54-114">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="e4a54-115">La opción `-codepage` no es necesaria si los archivos de código fuente se han guardado mediante la página actual de códigos ANSI, Unicode o UTF-8 con una firma.</span><span class="sxs-lookup"><span data-stu-id="e4a54-115">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="e4a54-116">De forma predeterminada, Visual Studio guarda todos los archivos de código fuente con la página de códigos ANSI actual, a menos que el usuario especifique otra codificación en el cuadro de diálogo **Codificación**.</span><span class="sxs-lookup"><span data-stu-id="e4a54-116">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="e4a54-117">Visual Studio usa el cuadro de diálogo **Codificación** para abrir los archivos de código fuente guardados con una página de códigos diferente.</span><span class="sxs-lookup"><span data-stu-id="e4a54-117">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4a54-118">La opción `-codepage` no está disponible en el entorno de desarrollo de Visual Studio; solo lo está cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="e4a54-118">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a54-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4a54-119">See also</span></span>

- [<span data-ttu-id="e4a54-120">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4a54-120">Visual Basic Command-Line Compiler</span></span>](index.md)
