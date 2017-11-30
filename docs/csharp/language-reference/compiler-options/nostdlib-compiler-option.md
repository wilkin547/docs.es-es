---
title: -nostdlib (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad3ca7775512623de43c7fe6b7fe1cf481ccca87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="nostdlib-c-compiler-options"></a><span data-ttu-id="0ade7-102">/nostdlib (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="0ade7-102">/nostdlib (C# Compiler Options)</span></span>
<span data-ttu-id="0ade7-103">**/nostdlib** impide la importación del archivo mscorlib.dll, que define el espacio de nombres System completo.</span><span class="sxs-lookup"><span data-stu-id="0ade7-103">**/nostdlib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ade7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ade7-104">Syntax</span></span>  
  
```console  
/nostdlib[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="0ade7-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0ade7-105">Remarks</span></span>  
 <span data-ttu-id="0ade7-106">Use esta opción si desea definir o crear sus propios objetos y espacio de nombres System.</span><span class="sxs-lookup"><span data-stu-id="0ade7-106">Use this option if you want to define or create your own System namespace and objects.</span></span>  
  
 <span data-ttu-id="0ade7-107">Si no se especifica **/nostdlib**, el archivo mscorlib.dll se importará en el programa (equivale a especificar **/nostdlib-**).</span><span class="sxs-lookup"><span data-stu-id="0ade7-107">If you do not specify **/nostdlib**, mscorlib.dll will be imported into your program (same as specifying **/nostdlib-**).</span></span> <span data-ttu-id="0ade7-108">Especificar **/nostdlib** es lo mismo que especificar **/nostdlib+**.</span><span class="sxs-lookup"><span data-stu-id="0ade7-108">Specifying **/nostdlib** is the same as specifying **/nostdlib+**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0ade7-109">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0ade7-109">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="0ade7-110">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0ade7-110">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="0ade7-111">Haga clic en la página de propiedades de **Compilar** .</span><span class="sxs-lookup"><span data-stu-id="0ade7-111">Click the **Build** properties page.</span></span>  
  
3.  <span data-ttu-id="0ade7-112">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="0ade7-112">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="0ade7-113">Modifique la propiedad **No hacer referencia al archivo mscorlib.dll** .</span><span class="sxs-lookup"><span data-stu-id="0ade7-113">Modify the **Do not reference mscorlib.dll** property.</span></span>  
  
 <span data-ttu-id="0ade7-114">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ade7-114">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ade7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ade7-115">See Also</span></span>  
 [<span data-ttu-id="0ade7-116">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="0ade7-116">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
