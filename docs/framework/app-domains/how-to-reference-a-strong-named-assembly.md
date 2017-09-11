---
title: "Cómo: Hacer referencia a un ensamblado con nombre seguro"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: aa46bfdfe42dca9509e39d4b6218473aa00a1877
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="461f5-102">Cómo: Hacer referencia a un ensamblado con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="461f5-102">How to: Reference a Strong-Named Assembly</span></span>
<span data-ttu-id="461f5-103">El proceso para hacer referencia a tipos o recursos en un ensamblado con nombre seguro suele ser transparente.</span><span class="sxs-lookup"><span data-stu-id="461f5-103">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="461f5-104">Puede hacer referencia en tiempo de compilación (enlace anticipado) o en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="461f5-104">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
 <span data-ttu-id="461f5-105">Una referencia en tiempo de compilación se produce cuando se le indica al compilador que el ensamblado hace referencia explícitamente a otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="461f5-105">A compile-time reference occurs when you indicate to the compiler that your assembly explicitly references another assembly.</span></span> <span data-ttu-id="461f5-106">Cuando se usan referencias en tiempo de compilación, el compilador obtiene automáticamente la clave pública del ensamblado con nombre seguro de destino y la coloca en la referencia del ensamblado que se está compilando.</span><span class="sxs-lookup"><span data-stu-id="461f5-106">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="461f5-107">Un ensamblado con nombre seguro solo puede usar tipos de otros ensamblados con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="461f5-107">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="461f5-108">De lo contrario, se pondría en peligro la seguridad del ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="461f5-108">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
### <a name="to-make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="461f5-109">Para hacer referencia en tiempo de compilación a un ensamblado con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="461f5-109">To make a compile-time reference to a strong-named assembly</span></span>  
  
1.  <span data-ttu-id="461f5-110">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="461f5-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="461f5-111">\<*compiler command*> **/reference:**\<*assembly name*></span><span class="sxs-lookup"><span data-stu-id="461f5-111">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  
  
     <span data-ttu-id="461f5-112">En este comando, *compiler command* es el comando del compilador para el lenguaje que está usando, y *assembly name* es el nombre del ensamblado con nombre seguro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="461f5-112">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="461f5-113">También puede usar otras opciones de compilador, como la opción **/t:library** para crear un ensamblado de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="461f5-113">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  
  
 <span data-ttu-id="461f5-114">En el ejemplo siguiente se crea un ensamblado denominado `myAssembly.dll` que hace referencia a un ensamblado con nombre seguro denominado `myLibAssembly.dll` desde un módulo de código denominado `myAssembly.cs`.</span><span class="sxs-lookup"><span data-stu-id="461f5-114">The following example creates an assembly called `myAssembly.dll` that references a strong-named assembly called `myLibAssembly.dll` from a code module called `myAssembly.cs`.</span></span>  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### <a name="to-make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="461f5-115">Para hacer referencia en tiempo de ejecución a un ensamblado con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="461f5-115">To make a run-time reference to a strong-named assembly</span></span>  
  
1.  <span data-ttu-id="461f5-116">Cuando se hace referencia en tiempo de ejecución a un ensamblado con nombre seguro (por ejemplo, mediante el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> o <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>), debe usar el nombre para mostrar del ensamblado con nombre seguro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="461f5-116">When you make a run-time reference to a strong-named assembly (for example, by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> method), you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="461f5-117">La sintaxis de un nombre para mostrar es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="461f5-117">The syntax of a display name is as follows:</span></span>  
  
     <span data-ttu-id="461f5-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span><span class="sxs-lookup"><span data-stu-id="461f5-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  
  
     <span data-ttu-id="461f5-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="461f5-119">For example:</span></span>  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     <span data-ttu-id="461f5-120">En este ejemplo, `PublicKeyToken` es la forma hexadecimal del token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="461f5-120">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="461f5-121">Si no hay ningún valor de referencia cultural, use `Culture=neutral`.</span><span class="sxs-lookup"><span data-stu-id="461f5-121">If there is no culture value, use `Culture=neutral`.</span></span>  
  
 <span data-ttu-id="461f5-122">En el ejemplo de código siguiente se muestra cómo usar esta información con el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="461f5-122">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="461f5-123">[!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)] [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)] [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="461f5-123">[!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)] [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)] [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]</span></span>  
  
 <span data-ttu-id="461f5-124">Puede imprimir el formato hexadecimal de la clave pública y el token de clave pública de un ensamblado concreto. Para ello, use el siguiente comando de la [herramienta de nombre seguro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md):</span><span class="sxs-lookup"><span data-stu-id="461f5-124">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  
  
 <span data-ttu-id="461f5-125">**sn -Tp \<** *assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="461f5-125">**sn -Tp \<** *assembly* **>**</span></span>  
  
 <span data-ttu-id="461f5-126">Si tiene un archivo de clave pública, puede usar en su lugar el comando siguiente (observe la diferencia en el caso de la opción de la línea de comandos):</span><span class="sxs-lookup"><span data-stu-id="461f5-126">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  
  
 <span data-ttu-id="461f5-127">**sn -tp \<** *assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="461f5-127">**sn -tp \<** *assembly* **>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="461f5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="461f5-128">See Also</span></span>  
 [<span data-ttu-id="461f5-129">Crear y utilizar ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="461f5-129">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

