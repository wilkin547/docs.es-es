---
title: -delaysign (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /delaysign
dev_langs:
- CSharp
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce4c9fbb14081764985f3b02988dff9ee272c451
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="delaysign-c-compiler-options"></a><span data-ttu-id="6ea18-102">/delaysign (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="6ea18-102">/delaysign (C# Compiler Options)</span></span>
<span data-ttu-id="6ea18-103">Esta opción hace que el compilador reserve espacio en el archivo de salida de manera que se pueda agregar una firma digital más adelante.</span><span class="sxs-lookup"><span data-stu-id="6ea18-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ea18-104">Syntax</span></span>  
  
```console  
/delaysign[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6ea18-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6ea18-105">Arguments</span></span>  
 <span data-ttu-id="6ea18-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="6ea18-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="6ea18-107">Use **/delaysign-** para firmar completamente un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ea18-107">Use **/delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="6ea18-108">Use **/delaysign+** si quiere incluir solo la clave pública en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6ea18-108">Use **/delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="6ea18-109">El valor predeterminado es **/delaysign-**.</span><span class="sxs-lookup"><span data-stu-id="6ea18-109">The default is **/delaysign-**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ea18-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ea18-110">Remarks</span></span>  
 <span data-ttu-id="6ea18-111">La opción **/delaysign** no tiene ningún efecto a menos que se use con [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) o [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6ea18-111">The **/delaysign** option has no effect unless used with [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) or [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span>  
  
 <span data-ttu-id="6ea18-112">Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada.</span><span class="sxs-lookup"><span data-stu-id="6ea18-112">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="6ea18-113">La firma digital resultante se almacena en el archivo que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="6ea18-113">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="6ea18-114">Cuando se retrasa la firma de un ensamblado, el compilador no calcula ni almacena la firma, sino que reserva espacio en el archivo para que la firma se pueda agregar más tarde.</span><span class="sxs-lookup"><span data-stu-id="6ea18-114">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="6ea18-115">Por ejemplo, si se usa **/delaysign+**, los evaluadores podrán colocar el ensamblado en la memoria caché global.</span><span class="sxs-lookup"><span data-stu-id="6ea18-115">For example, using **/delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="6ea18-116">Después de realizar las pruebas, coloque la clave privada en el ensamblado mediante la utilidad [Assembly Linker](https://msdn.microsoft.com/library/c405shex) para firmar el ensamblado por completo.</span><span class="sxs-lookup"><span data-stu-id="6ea18-116">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](https://msdn.microsoft.com/library/c405shex) utility.</span></span>  
  
 <span data-ttu-id="6ea18-117">Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](https://msdn.microsoft.com/library/xwb8f617) y [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md) (Retrasar la firma de un ensamblado).</span><span class="sxs-lookup"><span data-stu-id="6ea18-117">For more information, see [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="6ea18-118">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6ea18-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="6ea18-119">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6ea18-119">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="6ea18-120">Modifique la propiedad **Solo retrasar firma**.</span><span class="sxs-lookup"><span data-stu-id="6ea18-120">Modify the **Delay sign only** property.</span></span>  
  
 <span data-ttu-id="6ea18-121">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ea18-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea18-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ea18-122">See Also</span></span>  
 <span data-ttu-id="6ea18-123">[Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="6ea18-123">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="6ea18-124">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="6ea18-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

