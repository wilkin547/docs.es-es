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
ms.openlocfilehash: 3352e7fc446ace391540360a3b6b36d604ca5f13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173762"
---
# <a name="-codepage-c-compiler-options"></a><span data-ttu-id="78866-102">-codepage (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="78866-102">-codepage (C# Compiler Options)</span></span>
<span data-ttu-id="78866-103">Esta opción especifica qué página de códigos se va a usar durante la compilación si la página necesaria no es la página de códigos predeterminada actual del sistema.</span><span class="sxs-lookup"><span data-stu-id="78866-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78866-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78866-104">Syntax</span></span>  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="78866-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="78866-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="78866-106">El id. de la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="78866-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78866-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78866-107">Remarks</span></span>  
 <span data-ttu-id="78866-108">El compilador primero intenta interpretar todos los archivos de código fuente como UTF-8.</span><span class="sxs-lookup"><span data-stu-id="78866-108">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="78866-109">Si los archivos de código fuente se encuentran en una codificación distinta de UTF-8 y usan caracteres que no sean ASCII de 7 bits, emplee la opción **-codepage** para especificar qué página de códigos debe usarse.</span><span class="sxs-lookup"><span data-stu-id="78866-109">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **-codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="78866-110">**-codepage** se aplica a todos los archivos de código fuente de su compilación.</span><span class="sxs-lookup"><span data-stu-id="78866-110">**-codepage** applies to all source code files in your compilation.</span></span>  

 <span data-ttu-id="78866-111">Vea [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) para obtener información sobre cómo buscar las páginas de códigos que se admiten en su sistema.</span><span class="sxs-lookup"><span data-stu-id="78866-111">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="78866-112">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="78866-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78866-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="78866-113">See also</span></span>

- [<span data-ttu-id="78866-114">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="78866-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="78866-115">Administrar propiedades de proyectos y de soluciones</span><span class="sxs-lookup"><span data-stu-id="78866-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
