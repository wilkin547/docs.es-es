---
title: "Cómo: Registrar ensamblados de interoperabilidad primarios"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- registering primary interop assemblies
- primary interop assemblies, registering
ms.assetid: 4b2fcf8a-429d-43ce-8334-e026040be8bb
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6615abdf621217baa7ced4211bfa19abac944be9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-register-primary-interop-assemblies"></a><span data-ttu-id="7d180-102">Cómo: Registrar ensamblados de interoperabilidad primarios</span><span class="sxs-lookup"><span data-stu-id="7d180-102">How to: Register Primary Interop Assemblies</span></span>
<span data-ttu-id="7d180-103">Las clases solo se pueden serializar con la interoperabilidad COM y siempre se serializan como interfaces.</span><span class="sxs-lookup"><span data-stu-id="7d180-103">Classes can be marshaled only by COM interop and are always marshaled as interfaces.</span></span> <span data-ttu-id="7d180-104">En algunos casos, la interfaz usada para serializar la clase se conoce como interfaz de clase.</span><span class="sxs-lookup"><span data-stu-id="7d180-104">In some cases the interface used to marshal the class is known as the class interface.</span></span> <span data-ttu-id="7d180-105">Para obtener información sobre cómo invalidar la interfaz de clase con una interfaz de su elección, vea [Contenedor CCW](../../../docs/framework/interop/com-callable-wrapper.md).</span><span class="sxs-lookup"><span data-stu-id="7d180-105">For information about overriding the class interface with an interface of your choice, see [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md).</span></span>  
  
 <span data-ttu-id="7d180-106">Aunque cualquier desarrollador que quiera usar tipos COM en una aplicación .NET Framework puede generar un ensamblado de interoperabilidad, hacerlo supone un problema.</span><span class="sxs-lookup"><span data-stu-id="7d180-106">Although any developer who wants to use COM types from a .NET Framework application can generate an interop assembly, doing so creates a problem.</span></span> <span data-ttu-id="7d180-107">Cada vez que un desarrollador importa y firma una biblioteca de tipos COM, crea un conjunto de tipos únicos que son incompatibles con los que importe y firme otro programador.</span><span class="sxs-lookup"><span data-stu-id="7d180-107">Each time a developer imports and signs a COM type library, that developer creates a set of unique types that are incompatible with those imported and signed by another developer.</span></span> <span data-ttu-id="7d180-108">La solución a este problema de incompatibilidad de tipos es que cada desarrollador obtenga el ensamblado de interoperabilidad principal firmado y suministrado por el proveedor.</span><span class="sxs-lookup"><span data-stu-id="7d180-108">The solution to this type incompatibility problem is for each developer to obtain the vendor-supplied and signed primary interop assembly.</span></span>  
  
 <span data-ttu-id="7d180-109">Si tiene previsto exponer tipos COM de terceros en otras aplicaciones, use siempre el ensamblado de interoperabilidad primario proporcionado por el mismo editor que la biblioteca de tipos que define.</span><span class="sxs-lookup"><span data-stu-id="7d180-109">If you plan to expose third-party COM types to other applications, always use the primary interop assembly provided by the same publisher as the type library it defines.</span></span> <span data-ttu-id="7d180-110">Además de garantizar la compatibilidad de tipos, los ensamblados de interoperabilidad primarios suelen estar personalizados por el proveedor para mejorar la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="7d180-110">In addition to providing guaranteed type compatibility, primary interop assemblies are often customized by the vendor to enhance interoperability.</span></span>  
  
 <span data-ttu-id="7d180-111">Aunque no tenga pensado exponer tipos COM de terceros, el uso de ensamblados de interoperabilidad primarios puede facilitar la tarea de interoperar con componentes COM.</span><span class="sxs-lookup"><span data-stu-id="7d180-111">Even if you do not plan to expose third-party COM types, using the primary interop assembly can ease the task of interoperating with COM components.</span></span> <span data-ttu-id="7d180-112">Sin embargo, esta estrategia no ofrece aislamiento de los cambios que un proveedor pudiera hacer a los tipos definidos en un ensamblado de interoperabilidad primario.</span><span class="sxs-lookup"><span data-stu-id="7d180-112">However, this strategy provides no insulation from changes a vendor might make to types defined in a primary interop assembly.</span></span> <span data-ttu-id="7d180-113">Cuando la aplicación requiera dicho aislamiento, genere su propio ensamblado de interoperabilidad en lugar de usar el ensamblado de interoperabilidad primario.</span><span class="sxs-lookup"><span data-stu-id="7d180-113">When your application requires such insulation, generate your own interop assembly instead of using the primary interop assembly.</span></span>  
  
 <span data-ttu-id="7d180-114">Debe registrar todos los ensamblados de interoperabilidad primarios adquiridos en el equipo de desarrollo antes de hacer referencia a ellos con [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d180-114">You must register all acquired primary interop assemblies on your development computer before you can reference them with [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)].</span></span> <span data-ttu-id="7d180-115">Visual Studio busca y usa un ensamblado de interoperabilidad primario la primera vez que haga referencia a un tipo de una biblioteca de tipos COM.</span><span class="sxs-lookup"><span data-stu-id="7d180-115">Visual Studio looks for and uses a primary interop assembly the first time that you reference a type from a COM type library.</span></span> <span data-ttu-id="7d180-116">Si Visual Studio no encuentra el ensamblado de interoperabilidad primario asociado a la biblioteca de tipos, le pide que lo adquiera o le ofrece la posibilidad de crear un ensamblado de interoperabilidad en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7d180-116">If Visual Studio cannot locate the primary interop assembly associated with the type library, it prompts you to acquire it or offers to create an interop assembly instead.</span></span> <span data-ttu-id="7d180-117">Del mismo modo, el [Importador de la biblioteca de tipos (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) usa también el registro para buscar ensamblados de interoperabilidad primarios.</span><span class="sxs-lookup"><span data-stu-id="7d180-117">Likewise, the [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) also uses the registry to locate primary interop assemblies.</span></span>  
  
 <span data-ttu-id="7d180-118">Aunque no es necesario registrar los ensamblados de interoperabilidad primarios a menos que tenga pensado usar Visual Studio, registrarlos ofrece dos ventajas:</span><span class="sxs-lookup"><span data-stu-id="7d180-118">Although it is not necessary to register primary interop assemblies unless you plan to use Visual Studio, registration provides two advantages:</span></span>  
  
-   <span data-ttu-id="7d180-119">Un ensamblado de interoperabilidad primario registrado está marcado claramente bajo la clave del Registro de la biblioteca de tipos original.</span><span class="sxs-lookup"><span data-stu-id="7d180-119">A registered primary interop assembly is clearly marked under the registry key of the original type library.</span></span> <span data-ttu-id="7d180-120">Registrarlo es la mejor manera de encontrar un ensamblado de interoperabilidad primario en el equipo.</span><span class="sxs-lookup"><span data-stu-id="7d180-120">Registration is the best way for you to locate a primary interop assembly on your computer.</span></span>  
  
-   <span data-ttu-id="7d180-121">Puede evitar generar y usar un nuevo ensamblado de interoperabilidad accidentalmente si, en algún momento en el futuro, usa Visual Studio para hacer referencia a un tipo para el que tiene un ensamblado de interoperabilidad primario sin registrar.</span><span class="sxs-lookup"><span data-stu-id="7d180-121">You can avoid accidentally generating and using a new interop assembly if, at some time in the future, you do use Visual Studio to reference a type for which you have an unregistered primary interop assembly.</span></span>  
  
 <span data-ttu-id="7d180-122">Use la [herramienta Registro de ensamblados (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) para registrar un ensamblado de interoperabilidad primario.</span><span class="sxs-lookup"><span data-stu-id="7d180-122">Use the [Assembly Registration Tool (Regasm.exe)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) to register a primary interop assembly.</span></span>  
  
### <a name="to-register-a-primary-interop-assembly"></a><span data-ttu-id="7d180-123">Para registrar un ensamblado de interoperabilidad primario</span><span class="sxs-lookup"><span data-stu-id="7d180-123">To register a primary interop assembly</span></span>  
  
1.  <span data-ttu-id="7d180-124">En el símbolo del sistema, escriba:</span><span class="sxs-lookup"><span data-stu-id="7d180-124">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="7d180-125">**regasm** *nombre_de_ensamblado*</span><span class="sxs-lookup"><span data-stu-id="7d180-125">**regasm** *assemblyname*</span></span>  
  
     <span data-ttu-id="7d180-126">En este comando, *nombre_de_ensamblado* es el nombre de archivo del ensamblado que se va a registrar.</span><span class="sxs-lookup"><span data-stu-id="7d180-126">In this command, *assemblyname* is the file name of the assembly that is registered.</span></span> <span data-ttu-id="7d180-127">Regasm.exe agrega una entrada para el ensamblado de interoperabilidad primario bajo la misma clave del Registro que la biblioteca de tipos original.</span><span class="sxs-lookup"><span data-stu-id="7d180-127">Regasm.exe adds an entry for the primary interop assembly under the same registry key as the original type library.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d180-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d180-128">Example</span></span>  
 <span data-ttu-id="7d180-129">En el ejemplo siguiente se registra el ensamblado de interoperabilidad primario `CompanyA.UtilLib.dll`.</span><span class="sxs-lookup"><span data-stu-id="7d180-129">The following example registers the `CompanyA.UtilLib.dll` primary interop assembly.</span></span>  
  
```  
regasm CompanyA.UtilLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d180-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d180-130">See Also</span></span>  
 [<span data-ttu-id="7d180-131">Programar con ensamblados de interoperabilidad primarios</span><span class="sxs-lookup"><span data-stu-id="7d180-131">Programming with Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/306fa1d6-0703-4004-9e93-d0a57f1be81e)  
 [<span data-ttu-id="7d180-132">Buscar ensamblados de interoperabilidad primarios</span><span class="sxs-lookup"><span data-stu-id="7d180-132">Locating Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/d6768e4b-cd80-414d-a4f8-05d979eb393b)  
 [<span data-ttu-id="7d180-133">Redistribuir ensamblados de interoperabilidad primarios</span><span class="sxs-lookup"><span data-stu-id="7d180-133">Redistributing Primary Interop Assemblies</span></span>](http://msdn.microsoft.com/en-us/e76384f0-d631-474c-bdbd-13884cba0265)
