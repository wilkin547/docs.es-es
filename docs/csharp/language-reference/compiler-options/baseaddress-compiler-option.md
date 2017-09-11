---
title: -baseaddress (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /dllbase
dev_langs:
- CSharp
helpviewer_keywords:
- baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: 18
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
ms.openlocfilehash: 91193ae794957b5045a225614d6322e86d18d459
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="baseaddress-c-compiler-options"></a><span data-ttu-id="12a57-102">/baseaddress (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="12a57-102">/baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="12a57-103">La opción **/baseaddress** le permite especificar la dirección base preferida para cargar un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="12a57-103">The **/baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="12a57-104">Para obtener más información sobre cuándo y por qué usar esta opción, vea [Mejorar el tiempo de inicio de aplicación](http://go.microsoft.com/fwlink/?LinkId=107043) y [Blog de Larry Osterman](http://go.microsoft.com/fwlink/?LinkId=107044).</span><span class="sxs-lookup"><span data-stu-id="12a57-104">For more information about when and why to use this option, see [Improving Application Startup Time](http://go.microsoft.com/fwlink/?LinkId=107043) and [Larry Osterman's WebLog](http://go.microsoft.com/fwlink/?LinkId=107044).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12a57-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12a57-105">Syntax</span></span>  
  
```console  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="12a57-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="12a57-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="12a57-107">La dirección base del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="12a57-107">The base address for the DLL.</span></span> <span data-ttu-id="12a57-108">Esta dirección puede especificarse como un número octal, hexadecimal o decimal.</span><span class="sxs-lookup"><span data-stu-id="12a57-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12a57-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12a57-109">Remarks</span></span>  
 <span data-ttu-id="12a57-110">La dirección base predeterminada para un archivo DLL se establece mediante Common Language Runtime de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="12a57-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="12a57-111">Tenga en cuenta que la palabra de orden inferior en esta dirección se redondeará.</span><span class="sxs-lookup"><span data-stu-id="12a57-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="12a57-112">Por ejemplo, si especifica 0x11110001, se redondeará a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="12a57-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="12a57-113">Para completar el proceso de firma para un archivo DLL, use SN.EXE con la opción -R.</span><span class="sxs-lookup"><span data-stu-id="12a57-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="12a57-114">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="12a57-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="12a57-115">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="12a57-115">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="12a57-116">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="12a57-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="12a57-117">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="12a57-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="12a57-118">Modifique la propiedad **Dirección base del archivo DLL**.</span><span class="sxs-lookup"><span data-stu-id="12a57-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="12a57-119">Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="12a57-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12a57-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="12a57-120">See Also</span></span>  
 <span data-ttu-id="12a57-121"><xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="12a57-121"><xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="12a57-122">[Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="12a57-122">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="12a57-123">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="12a57-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

