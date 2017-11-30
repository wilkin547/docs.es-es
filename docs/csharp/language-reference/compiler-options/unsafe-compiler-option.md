---
title: -unsafe (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.assetid: fdb77ed9-da03-45bd-bb7f-250704da1bcc
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 146977522b400418a26f6a83e1a0ccdca8675bf9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="unsafe-c-compiler-options"></a><span data-ttu-id="3c4a0-102">/unsafe (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="3c4a0-102">/unsafe (C# Compiler Options)</span></span>
<span data-ttu-id="3c4a0-103">La opción del compilador **/unsafe** permite la compilación de código en el que se usa la palabra clave [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="3c4a0-103">The **/unsafe** compiler option allows code that uses the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword to compile.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c4a0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c4a0-104">Syntax</span></span>  
  
```console  
/unsafe  
```  
  
## <a name="remarks"></a><span data-ttu-id="3c4a0-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c4a0-105">Remarks</span></span>  
 <span data-ttu-id="3c4a0-106">Para obtener más información sobre el código no seguro, vea [Código no seguro y punteros](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="3c4a0-106">For more information about unsafe code, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="3c4a0-107">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3c4a0-107">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="3c4a0-108">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-108">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="3c4a0-109">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-109">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="3c4a0-110">Active la casilla **Permitir código no seguro**.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-110">Select the **Allow Unsafe Code** check box.</span></span>  
  
 <span data-ttu-id="3c4a0-111">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span><span class="sxs-lookup"><span data-stu-id="3c4a0-111">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c4a0-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c4a0-112">Example</span></span>  
 <span data-ttu-id="3c4a0-113">Compile `in.cs` para el modo no seguro:</span><span class="sxs-lookup"><span data-stu-id="3c4a0-113">Compile `in.cs` for unsafe mode:</span></span>  
  
```console  
csc /unsafe in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c4a0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c4a0-114">See Also</span></span>  
 [<span data-ttu-id="3c4a0-115">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="3c4a0-115">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="3c4a0-116">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="3c4a0-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
