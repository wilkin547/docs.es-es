---
title: "Cómo: Ver el contenido de un ensamblado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- assembly manifest, viewing information
- Ildasm.exe
- MSIL Disassembler
- assemblies [.NET Framework], viewing contents
- viewing assembly information
- MSIL
- viewing MSIL information
ms.assetid: fb7baaab-4c0d-47ad-8fd3-4591cf834709
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9c12c4811e8b23e86fca3960acdb4da06e38fbe
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-view-assembly-contents"></a><span data-ttu-id="afb41-102">Cómo: Ver el contenido de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="afb41-102">How to: View Assembly Contents</span></span>
<span data-ttu-id="afb41-103">Se puede usar [Ildasm.exe (Desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para ver la información del Lenguaje intermedio de Microsoft (MSIL) de un archivo.</span><span class="sxs-lookup"><span data-stu-id="afb41-103">You can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to view Microsoft intermediate language (MSIL) information in a file.</span></span> <span data-ttu-id="afb41-104">Si el archivo que se examina es un ensamblado, esta información puede incluir los atributos del ensamblado además de referencias a otros módulos y ensamblados.</span><span class="sxs-lookup"><span data-stu-id="afb41-104">If the file being examined is an assembly, this information can include the assembly's attributes, as well as references to other modules and assemblies.</span></span> <span data-ttu-id="afb41-105">Esta información puede ser útil para determinar si un archivo es un ensamblado o forma parte de uno y si el archivo tiene referencias a otros módulos o ensamblados.</span><span class="sxs-lookup"><span data-stu-id="afb41-105">This information can be helpful in determining whether a file is an assembly or part of an assembly, and whether the file has references to other modules or assemblies.</span></span>  
  
### <a name="to-display-the-contents-of-an-assembly-using-ildasmexe"></a><span data-ttu-id="afb41-106">Para mostrar el contenido de un ensamblado mediante Ildasm.exe</span><span class="sxs-lookup"><span data-stu-id="afb41-106">To display the contents of an assembly using Ildasm.exe</span></span>  
  
1.  <span data-ttu-id="afb41-107">Escriba **ildasm** \<*nombre de ensamblado*> en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="afb41-107">Type **ildasm** \<*assembly name*> at the command prompt.</span></span> <span data-ttu-id="afb41-108">Por ejemplo, el comando siguiente desensambla el ensamblado `Hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="afb41-108">For example, the following command disassembles the `Hello.exe` assembly.</span></span>  
  
    ```  
    ildasm Hello.exe  
    ```  
  
### <a name="to-view-assembly-manifest-information"></a><span data-ttu-id="afb41-109">Para ver información del manifiesto del ensamblado</span><span class="sxs-lookup"><span data-stu-id="afb41-109">To view assembly manifest information</span></span>  
  
1.  <span data-ttu-id="afb41-110">Haga doble clic en el icono del manifiesto en la ventana del Desensamblador de MSIL.</span><span class="sxs-lookup"><span data-stu-id="afb41-110">Double-click the MANIFEST icon in the MSIL Disassembler window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afb41-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="afb41-111">Example</span></span>  
 <span data-ttu-id="afb41-112">El ejemplo siguiente se inicia con un programa básico "Hello, World".</span><span class="sxs-lookup"><span data-stu-id="afb41-112">The following example starts with a basic "Hello, World" program.</span></span> <span data-ttu-id="afb41-113">Después de compilar el programa, use Ildasm.exe para desensamblar el ensamblado Hello.exe y ver el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="afb41-113">After compiling the program, use Ildasm.exe to disassemble the Hello.exe assembly and view the assembly manifest.</span></span>  
  
 [!code-cpp[Conceptual.Assembly.Contents#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.contents/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.Assembly.Contents#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.contents/cs/source.cs#1)]
 [!code-vb[Conceptual.Assembly.Contents#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.contents/vb/source.vb#1)]  
  
 <span data-ttu-id="afb41-114">Al ejecutar el comando ildasm.exe en el ensamblado Hello.exe y hacer doble clic en el icono del manifiesto en la ventana IL DASM se produce lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="afb41-114">Running the command ildasm.exe on the Hello.exe assembly and double-clicking the MANIFEST icon in the IL DASM window produces the following output:</span></span>  
  
```  
// Metadata version: v4.0.30319  
.assembly extern mscorlib  
{  
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..  
  .ver 4:0:0:0  
}  
.assembly Hello  
{  
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )   
  .custom instance void [mscorlib]System.Runtime.CompilerServices.RuntimeCompatibilityAttribute::.ctor() = ( 01 00 01 00 54 02 16 57 72 61 70 4E 6F 6E 45 78   // ....T..WrapNonEx  
                                                                                                             63 65 70 74 69 6F 6E 54 68 72 6F 77 73 01 )       // ceptionThrows.  
  .hash algorithm 0x00008004  
  .ver 0:0:0:0  
}  
.module Hello.exe  
// MVID: {7C2770DB-1594-438D-BAE5-98764C39CCCA}  
.imagebase 0x00400000  
.file alignment 0x00000200  
.stackreserve 0x00100000  
.subsystem 0x0003       // WINDOWS_CUI  
.corflags 0x00000001    //  ILONLY  
// Image base: 0x00600000  
```  
  
 <span data-ttu-id="afb41-115">En la tabla siguiente se explica cada directiva del manifiesto del ensamblado Hello.exe usado en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="afb41-115">The following table describes each directive in the assembly manifest of the Hello.exe assembly used in the example.</span></span>  
  
|<span data-ttu-id="afb41-116">Directiva</span><span class="sxs-lookup"><span data-stu-id="afb41-116">Directive</span></span>|<span data-ttu-id="afb41-117">Description</span><span class="sxs-lookup"><span data-stu-id="afb41-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="afb41-118">**.assembly extern \<** *nombre del ensamblado* **>**</span><span class="sxs-lookup"><span data-stu-id="afb41-118">**.assembly extern \<** *assembly name* **>**</span></span>|<span data-ttu-id="afb41-119">Especifica otro ensamblado que contiene elementos a los que hace referencia el módulo actual (en este ejemplo, `mscorlib`).</span><span class="sxs-lookup"><span data-stu-id="afb41-119">Specifies another assembly that contains items referenced by the current module (in this example, `mscorlib`).</span></span>|  
|<span data-ttu-id="afb41-120">**.publickeytoken \<** *token* **>**</span><span class="sxs-lookup"><span data-stu-id="afb41-120">**.publickeytoken \<** *token* **>**</span></span>|<span data-ttu-id="afb41-121">Especifica el token de la clave real del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="afb41-121">Specifies the token of the actual key of the referenced assembly.</span></span>|  
|<span data-ttu-id="afb41-122">**.ver \<** *número de versión* **>**</span><span class="sxs-lookup"><span data-stu-id="afb41-122">**.ver \<** *version number* **>**</span></span>|<span data-ttu-id="afb41-123">Especifica el número de versión del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="afb41-123">Specifies the version number of the referenced assembly.</span></span>|  
|<span data-ttu-id="afb41-124">**.assembly \<** *nombre del ensamblado* **>**</span><span class="sxs-lookup"><span data-stu-id="afb41-124">**.assembly \<** *assembly name* **>**</span></span>|<span data-ttu-id="afb41-125">Especifica el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="afb41-125">Specifies the assembly name.</span></span>|  
|<span data-ttu-id="afb41-126">**.hash algorithm \<** *valor int32* **>**</span><span class="sxs-lookup"><span data-stu-id="afb41-126">**.hash algorithm \<** *int32 value* **>**</span></span>|<span data-ttu-id="afb41-127">Especifica el algoritmo hash usado.</span><span class="sxs-lookup"><span data-stu-id="afb41-127">Specifies the hash algorithm used.</span></span>|  
|<span data-ttu-id="afb41-128">**.ver \<** *número de versión* **>**</span><span class="sxs-lookup"><span data-stu-id="afb41-128">**.ver \<** *version number* **>**</span></span>|<span data-ttu-id="afb41-129">Especifica el número de versión del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="afb41-129">Specifies the version number of the assembly.</span></span>|  
|<span data-ttu-id="afb41-130">**.module \<** *nombre del archivo* **>**</span><span class="sxs-lookup"><span data-stu-id="afb41-130">**.module \<** *file name* **>**</span></span>|<span data-ttu-id="afb41-131">Especifica el nombre de los módulos que componen el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="afb41-131">Specifies the name of the modules that make up the assembly.</span></span> <span data-ttu-id="afb41-132">En este ejemplo, el ensamblado consta de un único archivo.</span><span class="sxs-lookup"><span data-stu-id="afb41-132">In this example, the assembly consists of only one file.</span></span>|  
|<span data-ttu-id="afb41-133">**.subsystem \<** *valor* **>**</span><span class="sxs-lookup"><span data-stu-id="afb41-133">**.subsystem \<** *value* **>**</span></span>|<span data-ttu-id="afb41-134">Especifica el entorno de aplicación necesario para el programa.</span><span class="sxs-lookup"><span data-stu-id="afb41-134">Specifies the application environment required for the program.</span></span> <span data-ttu-id="afb41-135">En este ejemplo, el valor 3 indica que este ejecutable se ejecuta desde una consola.</span><span class="sxs-lookup"><span data-stu-id="afb41-135">In this example, the value 3 indicates that this executable is run from a console.</span></span>|  
|<span data-ttu-id="afb41-136">**.corflags**</span><span class="sxs-lookup"><span data-stu-id="afb41-136">**.corflags**</span></span>|<span data-ttu-id="afb41-137">De momento, un campo reservado de los metadatos.</span><span class="sxs-lookup"><span data-stu-id="afb41-137">Currently a reserved field in the metadata.</span></span>|  
  
 <span data-ttu-id="afb41-138">Un manifiesto de ensamblado puede contener varias directivas diferentes, según el contenido del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="afb41-138">An assembly manifest can contain a number of different directives, depending on the contents of the assembly.</span></span> <span data-ttu-id="afb41-139">Para obtener una lista completa de las directivas del manifiesto del ensamblado, vea la documentación de ECMA, especialmente "Partition II: Metadata Definition and Semantics (Partición II: definición y semántica de los metadatos)" y "Partition III: CIL Instruction Set (Partición III: conjunto de instrucciones CIL)".</span><span class="sxs-lookup"><span data-stu-id="afb41-139">For an extensive list of the directives in the assembly manifest, see the ECMA documentation, especially "Partition II: Metadata Definition and Semantics" and "Partition III: CIL Instruction Set".</span></span> <span data-ttu-id="afb41-140">La documentación está disponible en línea; vea [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) (Estándares de ECMA C# y Common Language Infrastructure) en MSDN y [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) (Estándar ECMA-335: Common Language Infrastructure [CLI]) en el sitio web de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="afb41-140">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb41-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="afb41-141">See Also</span></span>  
 [<span data-ttu-id="afb41-142">Dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="afb41-142">Application Domains and Assemblies</span></span>](http://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)  
 [<span data-ttu-id="afb41-143">Temas "Cómo..." sobre dominios de aplicación y ensamblados</span><span class="sxs-lookup"><span data-stu-id="afb41-143">Application Domains and Assemblies How-to Topics</span></span>](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 [<span data-ttu-id="afb41-144">Ildasm.exe (Desensamblador de IL)</span><span class="sxs-lookup"><span data-stu-id="afb41-144">Ildasm.exe (IL Disassembler)</span></span>](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)
