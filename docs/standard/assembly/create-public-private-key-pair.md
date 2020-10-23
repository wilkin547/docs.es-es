---
title: Procedimiento para crear un par de claves privada y pública
description: Aprenda a crear un par de claves criptográficas pública y privada para usarlo durante la compilación para crear un ensamblado con un nombre seguro.
ms.date: 08/20/2019
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: c42e98a7e27ded9a21445fae35ade843e834076a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163498"
---
# <a name="how-to-create-a-public-private-key-pair"></a><span data-ttu-id="e819a-103">Procedimiento para crear un par de claves privada y pública</span><span class="sxs-lookup"><span data-stu-id="e819a-103">How to: Create a public-private key pair</span></span>

<span data-ttu-id="e819a-104">Para firmar un ensamblado con un nombre seguro, debe disponer de un par de claves privada/pública.</span><span class="sxs-lookup"><span data-stu-id="e819a-104">To sign an assembly with a strong name, you must have a public/private key pair.</span></span> <span data-ttu-id="e819a-105">Este par de claves criptográficas pública y privada se utiliza durante la compilación para crear un ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="e819a-105">This public and private cryptographic key pair is used during compilation to create a strong-named assembly.</span></span> <span data-ttu-id="e819a-106">Puede crear un par de claves utilizando la [Herramienta Nombre seguro (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="e819a-106">You can create a key pair using the [Strong Name tool (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md).</span></span> <span data-ttu-id="e819a-107">Normalmente, los archivos de par de claves tienen la extensión *.snk*.</span><span class="sxs-lookup"><span data-stu-id="e819a-107">Key pair files usually have an *.snk* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="e819a-108">En Visual Studio, las páginas de propiedades de proyecto de C# y Visual Basic incluyen una pestaña **Firma** que le permite seleccionar los archivos de clave existentes o generar nuevos archivos de clave sin usar *Sn.exe*.</span><span class="sxs-lookup"><span data-stu-id="e819a-108">In Visual Studio, the C# and Visual Basic project property pages include a **Signing** tab that enables you to select existing key files or to generate new key files without using *Sn.exe*.</span></span> <span data-ttu-id="e819a-109">En Visual C++, puede especificar la ubicación de un archivo de clave existente en la página de propiedades **Avanzadas** de la sección **Vinculador** de la sección **Propiedades de configuración** de la ventana **Páginas de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e819a-109">In Visual C++, you can specify the location of an existing key file in the **Advanced** property page in the **Linker** section of the **Configuration Properties** section of the **Property Pages** window.</span></span> <span data-ttu-id="e819a-110">El uso del atributo <xref:System.Reflection.AssemblyKeyFileAttribute> para identificar los pares de archivo de clave se ha quedado obsoleto empezando por Visual Studio 2005.</span><span class="sxs-lookup"><span data-stu-id="e819a-110">The use of the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute to identify key file pairs was made obsolete beginning with Visual Studio 2005.</span></span>

## <a name="create-a-key-pair"></a><span data-ttu-id="e819a-111">Creación de un par de claves</span><span class="sxs-lookup"><span data-stu-id="e819a-111">Create a key pair</span></span>

<span data-ttu-id="e819a-112">Para crear un par de claves, en un símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e819a-112">To create a key pair, at a command prompt, type the following command:</span></span>

<span data-ttu-id="e819a-113">**sn –k** \<*file name*></span><span class="sxs-lookup"><span data-stu-id="e819a-113">**sn –k** \<*file name*></span></span>

<span data-ttu-id="e819a-114">En este comando, *nombre de archivo* es el nombre del archivo de salida que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="e819a-114">In this command, *file name* is the name of the output file containing the key pair.</span></span>

<span data-ttu-id="e819a-115">En el siguiente ejemplo se crea un par de claves denominado *sgKey.snk*.</span><span class="sxs-lookup"><span data-stu-id="e819a-115">The following example creates a key pair called *sgKey.snk*.</span></span>

```cmd
sn -k sgKey.snk
```

<span data-ttu-id="e819a-116">Si desea retrasar la firma de un ensamblado y controlar el par de claves completo (que es poco probable que esté fuera de los escenarios de prueba), puede usar los siguientes comandos para generar un par de claves y, a continuación, extraer la clave pública a partir de él en un archivo independiente.</span><span class="sxs-lookup"><span data-stu-id="e819a-116">If you intend to delay sign an assembly and you control the whole key pair (which is unlikely outside test scenarios), you can use the following commands to generate a key pair and then extract the public key from it into a separate file.</span></span> <span data-ttu-id="e819a-117">Primero, cree el par de claves:</span><span class="sxs-lookup"><span data-stu-id="e819a-117">First, create the key pair:</span></span>

```cmd
sn -k keypair.snk
```

<span data-ttu-id="e819a-118">A continuación, extraiga la clave pública del par de claves y cópiela en un archivo independiente:</span><span class="sxs-lookup"><span data-stu-id="e819a-118">Next, extract the public key from the key pair and copy it to a separate file:</span></span>

```cmd
sn -p keypair.snk public.snk
```

<span data-ttu-id="e819a-119">Una vez creado el par de claves, debe colocar el archivo donde las herramientas de inicio de sesión de nombre seguro puedan encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="e819a-119">Once you create the key pair, you must put the file where the strong name signing tools can find it.</span></span>

<span data-ttu-id="e819a-120">Al firmar un ensamblado con un nombre seguro, la [herramienta Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) busca el archivo de clave en relación con el directorio actual y el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="e819a-120">When signing an assembly with a strong name, the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) looks for the key file relative to the current directory and to the output directory.</span></span> <span data-ttu-id="e819a-121">Si se usan compiladores de la línea de comandos, no hay más que copiar la clave en el directorio actual que contenga los módulos de código.</span><span class="sxs-lookup"><span data-stu-id="e819a-121">When using command-line compilers, you can simply copy the key to the current directory containing your code modules.</span></span>

<span data-ttu-id="e819a-122">Si está usando una versión anterior de Visual Studio que no tiene una pestaña **Firma** en las propiedades del proyecto, la ubicación recomendada del archivo de clave es el directorio del proyecto con el atributo de archivo especificado de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="e819a-122">If you are using an earlier version of Visual Studio that does not have a **Signing** tab in the project properties, the recommended key file location is the project directory with the file attribute specified as follows:</span></span>

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

## <a name="see-also"></a><span data-ttu-id="e819a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e819a-123">See also</span></span>

- [<span data-ttu-id="e819a-124">Creación y uso de ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="e819a-124">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
