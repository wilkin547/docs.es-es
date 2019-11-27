---
title: -codepage
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: a38fb4be9347b3372b4a459fce2e96b9e38c3a51
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343543"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="5b4fa-102">-codePage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b4fa-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="5b4fa-103">Especifica la página de códigos que se va a utilizar para todos los archivos de código fuente en la compilación.</span><span class="sxs-lookup"><span data-stu-id="5b4fa-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b4fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b4fa-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="5b4fa-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5b4fa-105">Arguments</span></span>  
  
|<span data-ttu-id="5b4fa-106">Término</span><span class="sxs-lookup"><span data-stu-id="5b4fa-106">Term</span></span>|<span data-ttu-id="5b4fa-107">Definición</span><span class="sxs-lookup"><span data-stu-id="5b4fa-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="5b4fa-108">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="5b4fa-108">Required.</span></span> <span data-ttu-id="5b4fa-109">El compilador usa la página de códigos especificada por `id` para interpretar la codificación de los archivos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="5b4fa-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b4fa-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b4fa-110">Remarks</span></span>  
 <span data-ttu-id="5b4fa-111">Para compilar el código fuente guardado con una codificación específica, puede usar `-codepage` para especificar qué página de códigos debe usarse.</span><span class="sxs-lookup"><span data-stu-id="5b4fa-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="5b4fa-112">La opción `-codepage` se aplica a todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="5b4fa-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="5b4fa-113">Para obtener más información, vea [codificación de caracteres en el .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="5b4fa-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="5b4fa-114">La opción `-codepage` no es necesaria si los archivos de código fuente se guardaron mediante la página de códigos ANSI actual, Unicode o UTF-8 con una firma.</span><span class="sxs-lookup"><span data-stu-id="5b4fa-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="5b4fa-115">De forma predeterminada, Visual Studio guarda todos los archivos de código fuente con la página de códigos ANSI actual, a menos que el usuario especifique otra codificación en el cuadro de diálogo **codificación** .</span><span class="sxs-lookup"><span data-stu-id="5b4fa-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="5b4fa-116">Visual Studio usa el cuadro de diálogo **codificación** para abrir los archivos de código fuente guardados con una página de códigos diferente.</span><span class="sxs-lookup"><span data-stu-id="5b4fa-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b4fa-117">La opción `-codepage` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5b4fa-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b4fa-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b4fa-118">See also</span></span>

- [<span data-ttu-id="5b4fa-119">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b4fa-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
