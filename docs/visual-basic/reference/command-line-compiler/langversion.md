---
title: /langversion (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cfe91588471cc8410b25addea8d66a0388c9c5be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="langversion-visual-basic"></a><span data-ttu-id="90b9c-102">/langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90b9c-102">/langversion (Visual Basic)</span></span>
<span data-ttu-id="90b9c-103">Hace que el compilador acepte únicamente la sintaxis que se incluye en la versión de idioma de Visual Basic especificada.</span><span class="sxs-lookup"><span data-stu-id="90b9c-103">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90b9c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90b9c-104">Syntax</span></span>  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="90b9c-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="90b9c-105">Arguments</span></span>  
 `version`  
 <span data-ttu-id="90b9c-106">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="90b9c-106">Required.</span></span> <span data-ttu-id="90b9c-107">La versión de idioma que se usarán durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="90b9c-107">The language version to be used during the compilation.</span></span> <span data-ttu-id="90b9c-108">Valores aceptados son `9`, `9.0`, `10`, y `10.0`.</span><span class="sxs-lookup"><span data-stu-id="90b9c-108">Accepted values are `9`, `9.0`, `10`, and `10.0`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90b9c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="90b9c-109">Remarks</span></span>  
 <span data-ttu-id="90b9c-110">El `/langversion` opción especifica la sintaxis que el compilador acepta.</span><span class="sxs-lookup"><span data-stu-id="90b9c-110">The `/langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="90b9c-111">Por ejemplo, si especifica que la versión de lenguaje es 9.0, el compilador genera errores de sintaxis que es válida únicamente en la versión 10.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="90b9c-111">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>  
  
 <span data-ttu-id="90b9c-112">Puede usar esta opción para desarrollar aplicaciones destinadas a versiones diferentes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="90b9c-112">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="90b9c-113">Por ejemplo, si se establece como destino .NET Framework 3.5, podría utilizar esta opción para asegurarse de que no utilice la sintaxis de la versión de idioma 10.0.</span><span class="sxs-lookup"><span data-stu-id="90b9c-113">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>  
  
 <span data-ttu-id="90b9c-114">Puede establecer `/langversion` directamente únicamente mediante la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="90b9c-114">You can set `/langversion` directly only by using the command line.</span></span> <span data-ttu-id="90b9c-115">Para obtener más información, consulte [Elegir una versión específica de .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span><span class="sxs-lookup"><span data-stu-id="90b9c-115">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).</span></span>  
  
## <a name="example"></a><span data-ttu-id="90b9c-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90b9c-116">Example</span></span>  
 <span data-ttu-id="90b9c-117">El siguiente código compila `sample.vb` para Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="90b9c-117">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="90b9c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="90b9c-118">See Also</span></span>  
 [<span data-ttu-id="90b9c-119">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90b9c-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="90b9c-120">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="90b9c-120">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="90b9c-121">Elegir una versión específica de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="90b9c-121">Targeting a Specific .NET Framework Version</span></span>](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
