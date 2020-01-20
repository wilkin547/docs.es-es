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
ms.openlocfilehash: f138f445b8a335c7505e25b34f560c4da40ab2dd
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937209"
---
# <a name="-baseaddress-c-compiler-options"></a><span data-ttu-id="653ce-102">-baseaddress (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="653ce-102">-baseaddress (C# Compiler Options)</span></span>
<span data-ttu-id="653ce-103">La opción **-baseaddress** permite especificar la dirección base preferida para cargar un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="653ce-103">The **-baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="653ce-104">Para obtener más información sobre cuándo y por qué usar esta opción, vea el [blog de Larry Osterman](https://docs.microsoft.com/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span><span class="sxs-lookup"><span data-stu-id="653ce-104">For more information about when and why to use this option, see [Larry Osterman's WebLog](https://docs.microsoft.com/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="653ce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="653ce-105">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="653ce-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="653ce-106">Arguments</span></span>  
 `address`  
 <span data-ttu-id="653ce-107">La dirección base del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="653ce-107">The base address for the DLL.</span></span> <span data-ttu-id="653ce-108">Esta dirección puede especificarse como un número octal, hexadecimal o decimal.</span><span class="sxs-lookup"><span data-stu-id="653ce-108">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="653ce-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="653ce-109">Remarks</span></span>  
 <span data-ttu-id="653ce-110">La dirección base predeterminada para un archivo DLL se establece mediante Common Language Runtime de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="653ce-110">The default base address for a DLL is set by the .NET Framework common language runtime.</span></span>  
  
 <span data-ttu-id="653ce-111">Tenga en cuenta que la palabra de orden inferior en esta dirección se redondeará.</span><span class="sxs-lookup"><span data-stu-id="653ce-111">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="653ce-112">Por ejemplo, si especifica 0x11110001, se redondeará a 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="653ce-112">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="653ce-113">Para completar el proceso de firma para un archivo DLL, use SN.EXE con la opción -R.</span><span class="sxs-lookup"><span data-stu-id="653ce-113">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="653ce-114">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="653ce-114">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="653ce-115">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="653ce-115">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="653ce-116">Haga clic en la página de propiedades de **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="653ce-116">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="653ce-117">Haga clic en el botón **Avanzada** .</span><span class="sxs-lookup"><span data-stu-id="653ce-117">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="653ce-118">Modifique la propiedad **Dirección base del archivo DLL**.</span><span class="sxs-lookup"><span data-stu-id="653ce-118">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="653ce-119">Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="653ce-119">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="653ce-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="653ce-120">See also</span></span>

- <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>
- [<span data-ttu-id="653ce-121">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="653ce-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="653ce-122">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="653ce-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
