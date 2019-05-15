---
title: Procedimiento Determinar el nombre completo de un ensamblado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f1dbfde5e13d771f82ab1542e02de4c72b68678
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607742"
---
# <a name="how-to-determine-an-assemblys-fully-qualified-name"></a><span data-ttu-id="357c7-102">Procedimiento Determinar el nombre completo de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="357c7-102">How to: Determine an Assembly's Fully Qualified Name</span></span>
<span data-ttu-id="357c7-103">Para conocer el nombre completo de un ensamblado de la caché global de ensamblados, use la herramienta Caché global de ensamblados ([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="357c7-103">To discover the fully qualified name of an assembly in the global assembly cache, use the Global Assembly Cache Tool ([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md)).</span></span> <span data-ttu-id="357c7-104">Vea [Cómo: Consultar el contenido de la memoria caché global de ensamblados](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="357c7-104">See [How to: View the Contents of the Global Assembly Cache](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span></span>  
  
 <span data-ttu-id="357c7-105">En el caso de los ensamblados que no están en la caché global de ensamblados, puede obtener el nombre completo del ensamblado de varias formas: puede usar código para enviar la información a la consola o a una variable, o puede usar [Ildasm.exe (Desensamblador de MSIL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para examinar los metadatos del ensamblado, que contienen el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="357c7-105">For assemblies that are not in the global assembly cache, you can get the fully qualified assembly name in a number of ways: can use code to output the information to the console or to a variable, or you can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>  
  
- <span data-ttu-id="357c7-106">Si el ensamblado ya está cargado por la aplicación, puede recuperar el valor de la propiedad <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> para obtener el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="357c7-106">If the assembly is already loaded by the application, you can retrieve the value of the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property to get the fully qualified name.</span></span> <span data-ttu-id="357c7-107">Puede usar este enfoque tanto si el ensamblado está en la GAC como si no.</span><span class="sxs-lookup"><span data-stu-id="357c7-107">You can use this approach whether or not the assembly is in the GAC.</span></span> <span data-ttu-id="357c7-108">En este ejemplo se ilustra.</span><span class="sxs-lookup"><span data-stu-id="357c7-108">The example provides an illustration.</span></span>  
  
- <span data-ttu-id="357c7-109">Si conoce la ruta del sistema de archivos del ensamblado, puede llamar al método estático (`Shared` en Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> para obtener el nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="357c7-109">If you know the assembly's file system path, you can call the static (`Shared` in Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method to get the fully qualified assembly name.</span></span> <span data-ttu-id="357c7-110">Este es un ejemplo sencillo.</span><span class="sxs-lookup"><span data-stu-id="357c7-110">The following is a simple example.</span></span>  
  
     [!code-csharp[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/cs/getassemblyname1.cs#1)]
     [!code-vb[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/vb/getassemblyname1.vb#1)]  
  
- <span data-ttu-id="357c7-111">Puede usar [Ildasm.exe (Desensamblador de MSIL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para examinar los metadatos del ensamblado, que contiene el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="357c7-111">You can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>  
  
 <span data-ttu-id="357c7-112">Para más información sobre el establecimiento de atributos del ensamblado como la versión, la referencia cultural y el nombre de ensamblado, vea [Setting Assembly Attributes (Configurar atributos de ensamblados)](../../../docs/framework/app-domains/set-assembly-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="357c7-112">For more information about setting assembly attributes such as version, culture, and assembly name, see [Setting Assembly Attributes](../../../docs/framework/app-domains/set-assembly-attributes.md).</span></span> <span data-ttu-id="357c7-113">Para más información sobre cómo poner un nombre seguro a un ensamblado, vea [Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) (Crear y utilizar ensamblados con nombre seguro).</span><span class="sxs-lookup"><span data-stu-id="357c7-113">For more information about giving an assembly a strong name, see [Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="357c7-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="357c7-114">Example</span></span>  
 <span data-ttu-id="357c7-115">En el siguiente ejemplo de código se indica cómo mostrar el nombre completo de un ensamblado que contiene una clase especificada en la consola.</span><span class="sxs-lookup"><span data-stu-id="357c7-115">The following code example shows how to display the fully qualified name of an assembly containing a specified class to the console.</span></span> <span data-ttu-id="357c7-116">Como recupera el nombre de un ensamblado que la aplicación ya ha cargado, no importa si el ensamblado está en la GAC.</span><span class="sxs-lookup"><span data-stu-id="357c7-116">Because it retrieves the name of an assembly that the app has already loaded, it does not matter whether the assembly is in the GAC.</span></span>  
  
 [!code-cpp[Assembly.Fullname#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.FullName/CPP/example2.cpp#2)]
 [!code-csharp[Assembly.Fullname#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.FullName/CS/example2.cs#2)]
 [!code-vb[Assembly.Fullname#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.FullName/VB/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="357c7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="357c7-117">See also</span></span>

- [<span data-ttu-id="357c7-118">Nombres de ensamblado</span><span class="sxs-lookup"><span data-stu-id="357c7-118">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)
- [<span data-ttu-id="357c7-119">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="357c7-119">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)
- [<span data-ttu-id="357c7-120">Crear y utilizar ensamblados con nombre seguro</span><span class="sxs-lookup"><span data-stu-id="357c7-120">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="357c7-121">Caché global de ensamblados</span><span class="sxs-lookup"><span data-stu-id="357c7-121">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)
- [<span data-ttu-id="357c7-122">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="357c7-122">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="357c7-123">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="357c7-123">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
