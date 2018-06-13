---
title: 'Cómo: Crear un par de claves privada y pública'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe799e15655d4ae1d9d9b7303728b503a5e45082
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741755"
---
# <a name="how-to-create-a-public-private-key-pair"></a><span data-ttu-id="5e308-102">Cómo: Crear un par de claves privada y pública</span><span class="sxs-lookup"><span data-stu-id="5e308-102">How to: Create a Public-Private Key Pair</span></span>
<span data-ttu-id="5e308-103">Para firmar un ensamblado con un nombre seguro, debe disponer de un par de claves privada/pública.</span><span class="sxs-lookup"><span data-stu-id="5e308-103">To sign an assembly with a strong name, you must have a public/private key pair.</span></span> <span data-ttu-id="5e308-104">Este par de claves criptográficas pública y privada se utiliza durante la compilación para crear un ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="5e308-104">This public and private cryptographic key pair is used during compilation to create a strong-named assembly.</span></span> <span data-ttu-id="5e308-105">Puede crear un par de claves utilizando la [Herramienta Nombre seguro (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5e308-105">You can create a key pair using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).</span></span> <span data-ttu-id="5e308-106">Normalmente, los archivos de par de claves tienen la extensión snk.</span><span class="sxs-lookup"><span data-stu-id="5e308-106">Key pair files usually have an .snk extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e308-107">En Visual Studio, las páginas de propiedades de proyecto de C# y Visual Basic incluyen una pestaña **Firma** que le permite seleccionar los archivos de clave existentes o generar nuevos archivos de clave sin Sn.exe.</span><span class="sxs-lookup"><span data-stu-id="5e308-107">In Visual Studio, the C# and Visual Basic project property pages include a **Signing** tab that enables you to select existing key files or to generate new key files without using Sn.exe.</span></span> <span data-ttu-id="5e308-108">En Visual C++, puede especificar la ubicación de un archivo de clave existente en la página de propiedades **Avanzadas** de la sección **Vinculador** de la sección **Propiedades de configuración** de la ventana **Páginas de propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5e308-108">In Visual C++, you can specify the location of an existing key file in the **Advanced** property page in the **Linker** section of the **Configuration Properties** section of the **Property Pages** window.</span></span> <span data-ttu-id="5e308-109">El uso del atributo <xref:System.Reflection.AssemblyKeyFileAttribute> para identificar los pares de archivo de clave se ha quedado obsoleto empezando por [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e308-109">The use of the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute to identify key file pairs has been made obsolete beginning with [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span></span>  
  
### <a name="to-create-a-key-pair"></a><span data-ttu-id="5e308-110">Para crear un par de claves</span><span class="sxs-lookup"><span data-stu-id="5e308-110">To create a key pair</span></span>  
  
1.  <span data-ttu-id="5e308-111">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5e308-111">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="5e308-112">**sn –k** \<*nombre de archivo*></span><span class="sxs-lookup"><span data-stu-id="5e308-112">**sn –k** \<*file name*></span></span>  
  
     <span data-ttu-id="5e308-113">En este comando, *nombre de archivo* es el nombre del archivo de salida que contiene el par de claves.</span><span class="sxs-lookup"><span data-stu-id="5e308-113">In this command, *file name* is the name of the output file containing the key pair.</span></span>  
  
 <span data-ttu-id="5e308-114">En el siguiente ejemplo se crea un par de claves denominado `sgKey.snk`.</span><span class="sxs-lookup"><span data-stu-id="5e308-114">The following example creates a key pair called `sgKey.snk`.</span></span>  
  
```  
sn -k sgKey.snk  
```  
  
 <span data-ttu-id="5e308-115">Si desea retrasar la firma de un ensamblado y controlar el par de claves completo (que es poco probable que esté fuera de los escenarios de prueba), puede usar los siguientes comandos para generar un par de claves y, a continuación, extraer la clave pública a partir de él en un archivo independiente.</span><span class="sxs-lookup"><span data-stu-id="5e308-115">If you intend to delay sign an assembly and you control the whole key pair (which is unlikely outside test scenarios), you can use the following commands to generate a key pair and then extract the public key from it into a separate file.</span></span> <span data-ttu-id="5e308-116">Primero, cree el par de claves:</span><span class="sxs-lookup"><span data-stu-id="5e308-116">First, create the key pair:</span></span>  
  
```  
sn -k keypair.snk  
```  
  
 <span data-ttu-id="5e308-117">A continuación, extraiga la clave pública del par de claves y cópiela en un archivo independiente:</span><span class="sxs-lookup"><span data-stu-id="5e308-117">Next, extract the public key from the key pair and copy it to a separate file:</span></span>  
  
```  
sn -p keypair.snk public.snk  
```  
  
 <span data-ttu-id="5e308-118">Una vez creado el par de claves, debe colocar el archivo donde las herramientas de inicio de sesión de nombre seguro puedan encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="5e308-118">Once you create the key pair, you must put the file where the strong name signing tools can find it.</span></span>  
  
 <span data-ttu-id="5e308-119">Al firmar un ensamblado con un nombre seguro, la [herramienta Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) busca el archivo de clave en relación con el directorio actual y el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="5e308-119">When signing an assembly with a strong name, the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) looks for the key file relative to the current directory and to the output directory.</span></span> <span data-ttu-id="5e308-120">Si se usan compiladores de la línea de comandos, no hay más que copiar la clave en el directorio actual que contenga los módulos de código.</span><span class="sxs-lookup"><span data-stu-id="5e308-120">When using command-line compilers, you can simply copy the key to the current directory containing your code modules.</span></span>  
  
 <span data-ttu-id="5e308-121">Si está usando una versión anterior de Visual Studio que no tiene una pestaña **Firma** en las propiedades del proyecto, la ubicación recomendada del archivo de clave es el directorio del proyecto con el atributo de archivo especificado de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="5e308-121">If you are using an earlier version of Visual Studio that does not have a **Signing** tab in the project properties, the recommended key file location is the project directory with the file attribute specified as follows:</span></span>  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="5e308-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e308-122">See Also</span></span>  
 [<span data-ttu-id="5e308-123">Crear y utilizar ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="5e308-123">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
