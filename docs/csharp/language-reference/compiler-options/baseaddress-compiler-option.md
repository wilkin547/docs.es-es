---
title: -baseaddress (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
ms.openlocfilehash: 3759067731902ba4f460ff850fb5e81f2e544e99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33215237"
---
# <a name="-baseaddress-c-compiler-options"></a><span data-ttu-id="01721-102">-baseaddress (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="01721-102">-baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="01721-103">La opción **-baseaddress** permite especificar la dirección base preferida para cargar un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="01721-103">The **-baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="01721-104">Para obtener más información sobre cuándo y por qué usar esta opción, vea el [blog de Larry Osterman](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/).</span><span class="sxs-lookup"><span data-stu-id="01721-104">For more information about when and why to use this option, see [Larry Osterman's WebLog](https://blogs.msdn.microsoft.com/larryosterman/2004/07/06/why-should-i-even-bother-to-use-dlls-in-my-system/).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01721-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01721-105">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="01721-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="01721-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="01721-107">La dirección base del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="01721-107">The base address for the DLL.</span></span> <span data-ttu-id="01721-108">Esta dirección puede especificarse como un número octal, hexadecimal o decimal.</span><span class="sxs-lookup"><span data-stu-id="01721-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01721-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="01721-109">Remarks</span></span>  
 <span data-ttu-id="01721-110">La dirección base predeterminada para un archivo DLL se establece mediante Common Language Runtime de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="01721-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="01721-111">Tenga en cuenta que la palabra de orden inferior en esta dirección se redondeará.</span><span class="sxs-lookup"><span data-stu-id="01721-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="01721-112">Por ejemplo, si especifica 0x11110001, se redondeará a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="01721-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="01721-113">Para completar el proceso de firma para un archivo DLL, use SN.EXE con la opción -R.</span><span class="sxs-lookup"><span data-stu-id="01721-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="01721-114">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="01721-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="01721-115">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="01721-115">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="01721-116">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="01721-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="01721-117">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="01721-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="01721-118">Modifique la propiedad **Dirección base del archivo DLL**.</span><span class="sxs-lookup"><span data-stu-id="01721-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="01721-119">Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="01721-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01721-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="01721-120">See Also</span></span>  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="01721-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="01721-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="01721-122">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="01721-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
