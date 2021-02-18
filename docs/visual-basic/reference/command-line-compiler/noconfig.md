---
description: Más información sobre -noconfig
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: e97d44427b537e73a404a47d30db202e2c3b1f41
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481693"
---
# <a name="-noconfig"></a><span data-ttu-id="63c35-103">-noconfig</span><span class="sxs-lookup"><span data-stu-id="63c35-103">-noconfig</span></span>

<span data-ttu-id="63c35-104">Especifica que el compilador no debe hacer referencia automáticamente a los ensamblados de .NET Framework que se usan habitualmente ni importar los espacios de nombres `System` y `Microsoft.VisualBasic`.</span><span class="sxs-lookup"><span data-stu-id="63c35-104">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63c35-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63c35-105">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="63c35-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63c35-106">Remarks</span></span>  

 <span data-ttu-id="63c35-107">La opción `-noconfig` indica al compilador que no compile con el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe.</span><span class="sxs-lookup"><span data-stu-id="63c35-107">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="63c35-108">El archivo Vbc.rsp hace referencia a los ensamblados de .NET Framework que se usan habitualmente e importa los espacios de nombres `System` y `Microsoft.VisualBasic`.</span><span class="sxs-lookup"><span data-stu-id="63c35-108">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="63c35-109">El compilador hace referencia implícitamente al ensamblado System.dll a menos que se especifique la opción `-nostdlib`.</span><span class="sxs-lookup"><span data-stu-id="63c35-109">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="63c35-110">La opción `-nostdlib` indica al compilador que no compile con Vbc.rsp ni haga referencia automáticamente al ensamblado System.dll.</span><span class="sxs-lookup"><span data-stu-id="63c35-110">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63c35-111">Siempre se hace referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="63c35-111">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="63c35-112">El archivo Vbc.rsp se puede modificar para especificar más opciones de compilador que deben incluirse en todas las compilaciones de Vbc.exe (salvo si se especifica la opción `-noconfig`).</span><span class="sxs-lookup"><span data-stu-id="63c35-112">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="63c35-113">Para obtener más información, consulte [@ (especificar archivo de respuesta)](specify-response-file.md).</span><span class="sxs-lookup"><span data-stu-id="63c35-113">For more information, see [@ (Specify Response File)](specify-response-file.md).</span></span>  
  
 <span data-ttu-id="63c35-114">El compilador procesa en último lugar las opciones que se pasan al comando `vbc`.</span><span class="sxs-lookup"><span data-stu-id="63c35-114">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="63c35-115">Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="63c35-115">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63c35-116">La opción `-noconfig` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="63c35-116">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63c35-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="63c35-117">See also</span></span>

- [<span data-ttu-id="63c35-118">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63c35-118">-nostdlib (Visual Basic)</span></span>](nostdlib.md)
- [<span data-ttu-id="63c35-119">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63c35-119">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="63c35-120">@ (especificar archivo de respuesta)</span><span class="sxs-lookup"><span data-stu-id="63c35-120">@ (Specify Response File)</span></span>](specify-response-file.md)
- [<span data-ttu-id="63c35-121">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63c35-121">-reference (Visual Basic)</span></span>](reference.md)
