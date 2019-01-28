---
title: -codepage (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 7cbd3ec1b2d134106c6c9429341f5603444dac27
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693988"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="9df8e-102">-codepage (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="9df8e-102">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="9df8e-103">Esta opción especifica qué página de códigos se va a usar durante la compilación si la página necesaria no es la página de códigos predeterminada actual del sistema.</span><span class="sxs-lookup"><span data-stu-id="9df8e-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9df8e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9df8e-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="9df8e-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9df8e-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="9df8e-106">El id. de la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="9df8e-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9df8e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9df8e-107">Remarks</span></span>  
 <span data-ttu-id="9df8e-108">Si compila uno o más archivos de código fuente que no se han creado para usar la página de códigos predeterminada en su equipo, puede usar la opción **-codepage** para especificar qué página de códigos debe usarse.</span><span class="sxs-lookup"><span data-stu-id="9df8e-108">If you compile one or more source code files that were not created to use the default code page on your computer, you can use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="9df8e-109">**-codepage** se aplica a todos los archivos de código fuente de su compilación.</span><span class="sxs-lookup"><span data-stu-id="9df8e-109">**-codepage** applies to all source code files in your compilation.</span></span>  
  
 <span data-ttu-id="9df8e-110">Si los archivos de código fuente se han creado con la misma página de códigos que está en vigor en su equipo o si los archivos de código fuente se han creado con UNICODE o UTF-8, no necesita usar **-codepage**.</span><span class="sxs-lookup"><span data-stu-id="9df8e-110">If the source code files were created with the same codepage that is in effect on your computer or if the source code files were created with UNICODE or UTF-8, you need not use **-codepage**.</span></span>  
  
 <span data-ttu-id="9df8e-111">Vea [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) para obtener información sobre cómo buscar las páginas de códigos que se admiten en su sistema.</span><span class="sxs-lookup"><span data-stu-id="9df8e-111">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="9df8e-112">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="9df8e-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9df8e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9df8e-113">See also</span></span>

- [<span data-ttu-id="9df8e-114">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="9df8e-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="9df8e-115">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="9df8e-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
