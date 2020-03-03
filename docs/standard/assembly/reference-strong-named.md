---
title: Procedimiento para hacer referencia a un ensamblado con nombre seguro
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: adda4ed2ab5c59e3518b8e724044529a79840ad0
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156483"
---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="67e84-102">Procedimiento para hacer referencia a un ensamblado con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="67e84-102">How to: Reference a strong-named assembly</span></span>
<span data-ttu-id="67e84-103">El proceso para hacer referencia a tipos o recursos en un ensamblado con nombre seguro suele ser transparente.</span><span class="sxs-lookup"><span data-stu-id="67e84-103">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="67e84-104">Puede hacer referencia en tiempo de compilación (enlace anticipado) o en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="67e84-104">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
<span data-ttu-id="67e84-105">Una referencia en tiempo de compilación se produce cuando se le indica al compilador que el ensamblado que se va a compilar hace referencia explícitamente a otro ensamblado.</span><span class="sxs-lookup"><span data-stu-id="67e84-105">A compile-time reference occurs when you indicate to the compiler that the assembly to be compiled explicitly references another assembly.</span></span> <span data-ttu-id="67e84-106">Cuando se usan referencias en tiempo de compilación, el compilador obtiene automáticamente la clave pública del ensamblado con nombre seguro de destino y la coloca en la referencia del ensamblado que se está compilando.</span><span class="sxs-lookup"><span data-stu-id="67e84-106">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="67e84-107">Un ensamblado con nombre seguro solo puede usar tipos de otros ensamblados con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="67e84-107">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="67e84-108">De lo contrario, se pondría en peligro la seguridad del ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="67e84-108">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="67e84-109">Creación de una referencia en tiempo de compilación a un ensamblado con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="67e84-109">Make a compile-time reference to a strong-named assembly</span></span>  

<span data-ttu-id="67e84-110">En un símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="67e84-110">At a command prompt, type the following command:</span></span>  

<span data-ttu-id="67e84-111">\<*compiler command*> **/reference:**\<*assembly name*></span><span class="sxs-lookup"><span data-stu-id="67e84-111">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  

<span data-ttu-id="67e84-112">En este comando, *compiler command* es el comando del compilador para el lenguaje que está usando, y *assembly name* es el nombre del ensamblado con nombre seguro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67e84-112">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="67e84-113">También puede usar otras opciones de compilador, como la opción **/t:library** para crear un ensamblado de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="67e84-113">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  

<span data-ttu-id="67e84-114">En el ejemplo siguiente se crea un ensamblado denominado *myAssembly.dll* que hace referencia a un ensamblado con nombre seguro llamado *myLibAssembly.dll* desde el módulo de código *myAssembly.cs*.</span><span class="sxs-lookup"><span data-stu-id="67e84-114">The following example creates an assembly called *myAssembly.dll* that references a strong-named assembly called *myLibAssembly.dll* from a code module called *myAssembly.cs*.</span></span>  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="67e84-115">Creación de una referencia en tiempo de ejecución a un ensamblado con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="67e84-115">Make a run-time reference to a strong-named assembly</span></span>  
  
<span data-ttu-id="67e84-116">Cuando se crea una referencia en tiempo de ejecución a un ensamblado con nombre seguro (por ejemplo, mediante el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> o <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>), debe usar el nombre para mostrar del ensamblado con nombre seguro al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="67e84-116">When you make a run-time reference to a strong-named assembly, for example by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> method, you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="67e84-117">La sintaxis de un nombre para mostrar es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="67e84-117">The syntax of a display name is as follows:</span></span>  

<span data-ttu-id="67e84-118">\<*nombre del ensamblado*>**,** \<*número de versión*>**,** \<*referencia cultural*>**,** \<*token de clave pública*></span><span class="sxs-lookup"><span data-stu-id="67e84-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  

<span data-ttu-id="67e84-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="67e84-119">For example:</span></span>  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

<span data-ttu-id="67e84-120">En este ejemplo, `PublicKeyToken` es la forma hexadecimal del token de clave pública.</span><span class="sxs-lookup"><span data-stu-id="67e84-120">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="67e84-121">Si no hay ningún valor de referencia cultural, use `Culture=neutral`.</span><span class="sxs-lookup"><span data-stu-id="67e84-121">If there is no culture value, use `Culture=neutral`.</span></span>  

<span data-ttu-id="67e84-122">En el ejemplo de código siguiente se muestra cómo usar esta información con el método <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="67e84-122">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  

```cpp
Assembly^ myDll =
    Assembly::Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```csharp
Assembly myDll =
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```vb
Dim myDll As Assembly = _
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1")
```

<span data-ttu-id="67e84-123">Puede imprimir el formato hexadecimal de la clave pública y el token de clave pública de un ensamblado concreto. Para ello, use el siguiente comando de la [herramienta de nombre seguro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md):</span><span class="sxs-lookup"><span data-stu-id="67e84-123">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  

<span data-ttu-id="67e84-124">**sn -Tp \<** *ensamblado* **>**</span><span class="sxs-lookup"><span data-stu-id="67e84-124">**sn -Tp \<** *assembly* **>**</span></span>  

<span data-ttu-id="67e84-125">Si tiene un archivo de clave pública, puede usar en su lugar el comando siguiente (observe la diferencia en el caso de la opción de la línea de comandos):</span><span class="sxs-lookup"><span data-stu-id="67e84-125">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  

<span data-ttu-id="67e84-126">**sn -tp \<** *archivo de clave pública* **>**</span><span class="sxs-lookup"><span data-stu-id="67e84-126">**sn -tp \<** *public key file* **>**</span></span>  

## <a name="see-also"></a><span data-ttu-id="67e84-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="67e84-127">See also</span></span>

- [<span data-ttu-id="67e84-128">Creación y uso de ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="67e84-128">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
