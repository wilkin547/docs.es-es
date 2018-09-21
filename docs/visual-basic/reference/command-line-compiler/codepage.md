---
title: -codepage (Visual Basic)
ms.date: 03/09/2018
helpviewer_keywords:
- -codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
ms.openlocfilehash: fda75383435fdff718d1d50bc8583afc9858e7e2
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562182"
---
# <a name="-codepage-visual-basic"></a><span data-ttu-id="647ee-102">-codepage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="647ee-102">-codepage (Visual Basic)</span></span>
<span data-ttu-id="647ee-103">Especifica la página de códigos que se va a utilizar para todos los archivos de código fuente en la compilación.</span><span class="sxs-lookup"><span data-stu-id="647ee-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="647ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="647ee-104">Syntax</span></span>  
  
```  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="647ee-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="647ee-105">Arguments</span></span>  
  
|<span data-ttu-id="647ee-106">Término</span><span class="sxs-lookup"><span data-stu-id="647ee-106">Term</span></span>|<span data-ttu-id="647ee-107">Definición</span><span class="sxs-lookup"><span data-stu-id="647ee-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="647ee-108">Requerido.</span><span class="sxs-lookup"><span data-stu-id="647ee-108">Required.</span></span> <span data-ttu-id="647ee-109">El compilador usa la página de códigos especificada por `id` para interpretar la codificación de los archivos de origen.</span><span class="sxs-lookup"><span data-stu-id="647ee-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="647ee-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="647ee-110">Remarks</span></span>  
 <span data-ttu-id="647ee-111">Para compilar código fuente guardado con una codificación específica, puede usar `-codepage` para especificar qué página de códigos debe usarse.</span><span class="sxs-lookup"><span data-stu-id="647ee-111">To compile source code saved with a specific encoding, you can use `-codepage` to specify which code page should be used.</span></span> <span data-ttu-id="647ee-112">El `-codepage` opción se aplica a todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="647ee-112">The `-codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="647ee-113">Para obtener más información, consulte [codificación de caracteres en .NET Framework](../../../standard/base-types/character-encoding.md).</span><span class="sxs-lookup"><span data-stu-id="647ee-113">For more information, see [Character Encoding in the .NET Framework](../../../standard/base-types/character-encoding.md).</span></span>  
  
 <span data-ttu-id="647ee-114">El `-codepage` opción no es necesario si se guardaron los archivos de código fuente utilizando la página de códigos ANSI actual, Unicode o UTF-8 con una firma.</span><span class="sxs-lookup"><span data-stu-id="647ee-114">The `-codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> <span data-ttu-id="647ee-115">Visual Studio guarda todos los archivos de código fuente con la página de códigos ANSI actual de forma predeterminada, a menos que el usuario especifique otra codificación en el **Encoding** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="647ee-115">Visual Studio saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> <span data-ttu-id="647ee-116">Visual Studio usa el **Encoding** cuadro de diálogo para abrir archivos de código fuente que se guardan con una página de códigos diferentes.</span><span class="sxs-lookup"><span data-stu-id="647ee-116">Visual Studio uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="647ee-117">El `-codepage` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="647ee-117">The `-codepage` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="647ee-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="647ee-118">See also</span></span>

- [<span data-ttu-id="647ee-119">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="647ee-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
