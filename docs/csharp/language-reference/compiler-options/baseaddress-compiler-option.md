---
title: -baseaddress (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7cd3269754f783ab8b26683f5215aa81825673e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="baseaddress-c-compiler-options"></a><span data-ttu-id="ff94d-102">/baseaddress (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="ff94d-102">/baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="ff94d-103">La opción **/baseaddress** le permite especificar la dirección base preferida para cargar un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="ff94d-103">The **/baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="ff94d-104">Para obtener más información acerca de cuándo y por qué utilizar esta opción, vea [WebLog de Larry Osterman](http://go.microsoft.com/fwlink/?LinkId=107044).</span><span class="sxs-lookup"><span data-stu-id="ff94d-104">For more information about when and why to use this option, see [Larry Osterman's WebLog](http://go.microsoft.com/fwlink/?LinkId=107044).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff94d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff94d-105">Syntax</span></span>  
  
```console  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff94d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ff94d-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="ff94d-107">La dirección base del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="ff94d-107">The base address for the DLL.</span></span> <span data-ttu-id="ff94d-108">Esta dirección puede especificarse como un número octal, hexadecimal o decimal.</span><span class="sxs-lookup"><span data-stu-id="ff94d-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff94d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff94d-109">Remarks</span></span>  
 <span data-ttu-id="ff94d-110">La dirección base predeterminada para un archivo DLL se establece mediante Common Language Runtime de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff94d-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="ff94d-111">Tenga en cuenta que la palabra de orden inferior en esta dirección se redondeará.</span><span class="sxs-lookup"><span data-stu-id="ff94d-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="ff94d-112">Por ejemplo, si especifica 0x11110001, se redondeará a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="ff94d-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="ff94d-113">Para completar el proceso de firma para un archivo DLL, use SN.EXE con la opción -R.</span><span class="sxs-lookup"><span data-stu-id="ff94d-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="ff94d-114">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ff94d-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="ff94d-115">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ff94d-115">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="ff94d-116">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="ff94d-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="ff94d-117">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="ff94d-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="ff94d-118">Modifique la propiedad **Dirección base del archivo DLL**.</span><span class="sxs-lookup"><span data-stu-id="ff94d-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="ff94d-119">Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff94d-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff94d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff94d-120">See Also</span></span>  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="ff94d-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="ff94d-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="ff94d-122">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="ff94d-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
