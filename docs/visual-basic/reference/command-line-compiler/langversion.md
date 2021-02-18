---
description: Más información sobre -langversion (Visual Basic)
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.custom: updateeachrelease
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 52bf910e5d6f579ec535d9de5698a8921f058002
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466866"
---
# <a name="-langversion-visual-basic"></a><span data-ttu-id="d45ab-103">-langversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d45ab-103">-langversion (Visual Basic)</span></span>

<span data-ttu-id="d45ab-104">Hace que el compilador acepte solo la sintaxis que se incluye en la especificación elegida del lenguaje Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d45ab-104">Causes the compiler to accept only syntax that is included in the specified Visual Basic language version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d45ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d45ab-105">Syntax</span></span>  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a><span data-ttu-id="d45ab-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d45ab-106">Arguments</span></span>

 `version`\
 <span data-ttu-id="d45ab-107">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d45ab-107">Required.</span></span> <span data-ttu-id="d45ab-108">La versión del lenguaje que se va a usar durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="d45ab-108">The language version to be used during the compilation.</span></span> <span data-ttu-id="d45ab-109">Los valores aceptados son `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `16`, `default` y `latest`.</span><span class="sxs-lookup"><span data-stu-id="d45ab-109">Accepted values are `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `16`, `default` and `latest`.</span></span>

 <span data-ttu-id="d45ab-110">También se puede especificar cualquiera de los números enteros mediante `.0` como la versión secundaria, por ejemplo, `11.0`.</span><span class="sxs-lookup"><span data-stu-id="d45ab-110">Any of the whole numbers may also be specified using `.0` as the minor version, for example, `11.0`.</span></span>

 <span data-ttu-id="d45ab-111">Puede ver la lista de todos los valores posibles si especifica `-langversion:?` en la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d45ab-111">You can see the list of all possible values by specifying `-langversion:?` on the command line.</span></span>

## <a name="remarks"></a><span data-ttu-id="d45ab-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d45ab-112">Remarks</span></span>

<span data-ttu-id="d45ab-113">La opción `-langversion` especifica qué sintaxis acepta el compilador.</span><span class="sxs-lookup"><span data-stu-id="d45ab-113">The `-langversion` option specifies what syntax the compiler accepts.</span></span> <span data-ttu-id="d45ab-114">Por ejemplo, si especifica que la versión del lenguaje es la 9.0, el compilador genera errores para la sintaxis que solo es válida en la versión 10.0 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="d45ab-114">For example, if you specify that the language version is 9.0, the compiler generates errors for syntax that is valid only in version 10.0 and later.</span></span>

<span data-ttu-id="d45ab-115">Puede usar esta opción cuando desarrolle aplicaciones destinadas a versiones diferentes de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d45ab-115">You can use this option when you develop applications that target different versions of the .NET Framework.</span></span> <span data-ttu-id="d45ab-116">Por ejemplo, si selecciona .NET Framework 3.5 como destino, puede usar esta opción para asegurarse de que no usa la sintaxis de la versión 10.0 del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d45ab-116">For example, if you are targeting .NET Framework 3.5, you could use this option to ensure that you do not use syntax from language version 10.0.</span></span>

<span data-ttu-id="d45ab-117">Solo puede establecer `-langversion` directamente con la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d45ab-117">You can set `-langversion` directly only by using the command line.</span></span> <span data-ttu-id="d45ab-118">Para obtener más información, consulte [Elegir una versión específica de .NET Framework](/visualstudio/ide/visual-studio-multi-targeting-overview).</span><span class="sxs-lookup"><span data-stu-id="d45ab-118">For more information, see [Targeting a Specific .NET Framework Version](/visualstudio/ide/visual-studio-multi-targeting-overview).</span></span>

## <a name="example"></a><span data-ttu-id="d45ab-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d45ab-119">Example</span></span>

<span data-ttu-id="d45ab-120">El código siguiente compila `sample.vb` para Visual Basic 9.0.</span><span class="sxs-lookup"><span data-stu-id="d45ab-120">The following code compiles `sample.vb` for Visual Basic 9.0.</span></span>

```console
vbc -langversion:9.0 sample.vb
```

## <a name="see-also"></a><span data-ttu-id="d45ab-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d45ab-121">See also</span></span>

- [<span data-ttu-id="d45ab-122">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d45ab-122">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="d45ab-123">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d45ab-123">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
