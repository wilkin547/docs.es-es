---
title: "Cómo: Crear contenedores COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8f8e5ef6aa90b1d31c589a82891f0ca1bfa5469
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="6bc75-102">Cómo: Crear contenedores COM</span><span class="sxs-lookup"><span data-stu-id="6bc75-102">How to: Create COM Wrappers</span></span>
<span data-ttu-id="6bc75-103">Puede crear contenedores del Modelo de objetos componentes (COM) mediante características de [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] o las herramientas Tlbimp.exe y Regasm.exe de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6bc75-103">You can create Component Object Model (COM) wrappers by using [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="6bc75-104">Ambos métodos generan dos tipos de contenedores COM:</span><span class="sxs-lookup"><span data-stu-id="6bc75-104">Both methods generate two types of COM wrappers:</span></span>  
  
-   <span data-ttu-id="6bc75-105">Un [contenedor RCW](../../../docs/framework/interop/runtime-callable-wrapper.md) desde una biblioteca de tipos para ejecutar un objeto COM en código administrado.</span><span class="sxs-lookup"><span data-stu-id="6bc75-105">A [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>  
  
-   <span data-ttu-id="6bc75-106">Un [contenedor CCW](../../../docs/framework/interop/com-callable-wrapper.md) con la configuración del Registro necesaria para ejecutar un objeto administrado en una aplicación nativa.</span><span class="sxs-lookup"><span data-stu-id="6bc75-106">A [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>  
  
 <span data-ttu-id="6bc75-107">En [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], puede agregar el contenedor COM como una referencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="6bc75-107">In [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], you can add the COM wrapper as a reference to your project.</span></span>  
  
## <a name="wrapping-com-objects-in-a-managed-application"></a><span data-ttu-id="6bc75-108">Encapsulación de objetos COM en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="6bc75-108">Wrapping COM Objects in a Managed Application</span></span>  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="6bc75-109">Para crear un contenedor RCW con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6bc75-109">To create a runtime callable wrapper using Visual Studio</span></span>  
  
1.  <span data-ttu-id="6bc75-110">Abra el proyecto de la aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="6bc75-110">Open the project for your managed application.</span></span>  
  
2.  <span data-ttu-id="6bc75-111">En el menú **Proyecto**, haga clic en **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="6bc75-111">On the **Project** menu, click **Show All Files**.</span></span>  
  
3.  <span data-ttu-id="6bc75-112">En el menú **Proyecto**, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="6bc75-112">On the **Project** menu, click **Add Reference**.</span></span>  
  
4.  <span data-ttu-id="6bc75-113">En el cuadro de diálogo Agregar referencia, haga clic en la pestaña **COM**, seleccione el componente que quiera usar y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6bc75-113">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>  
  
     <span data-ttu-id="6bc75-114">En el **Explorador de soluciones**, tenga en cuenta que el componente COM se agrega a la carpeta Referencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6bc75-114">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>  
  
 <span data-ttu-id="6bc75-115">Ahora puede escribir código para tener acceso al objeto COM.</span><span class="sxs-lookup"><span data-stu-id="6bc75-115">You can now write code to access the COM object.</span></span> <span data-ttu-id="6bc75-116">Puede comenzar declarando el objeto, por ejemplo con una instrucción `Imports` para [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] o una instrucción `Using` para [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bc75-116">You can begin by declaring the object, such as with an `Imports` statement for [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] or a `Using` statement for [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bc75-117">Si quiere programar componentes de Microsoft Office, instale primero los [ensamblados de interoperabilidad primarios de Microsoft Office](http://go.microsoft.com/fwlink/?LinkId=50479) (PIA) desde el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6bc75-117">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies](http://go.microsoft.com/fwlink/?LinkId=50479) (PIAs) from the Microsoft Download Center.</span></span> <span data-ttu-id="6bc75-118">En el paso 4, seleccione la versión más reciente de la biblioteca de objetos disponible para el producto de Office que quiere, como la **biblioteca de objetos de Microsoft Word 11.0**.</span><span class="sxs-lookup"><span data-stu-id="6bc75-118">In step 4, select the latest version of the object library available for the Office product you want, such as the **Microsoft Word 11.0 Object Library**.</span></span>  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="6bc75-119">Para crear un contenedor RCW mediante las herramientas de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6bc75-119">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
-   <span data-ttu-id="6bc75-120">Ejecute la herramienta [TlbImp.exe (Importador de la biblioteca de tipos)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="6bc75-120">Run the [Tlbimp.exe (Type Library Importer)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="6bc75-121">Esta herramienta crea un ensamblado que contiene los metadatos de tiempo de ejecución para los tipos definidos en la biblioteca de tipos original.</span><span class="sxs-lookup"><span data-stu-id="6bc75-121">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrapping-managed-objects-in-a-native-application"></a><span data-ttu-id="6bc75-122">Encapsular objetos administrados en una aplicación nativa</span><span class="sxs-lookup"><span data-stu-id="6bc75-122">Wrapping Managed Objects in a Native Application</span></span>  
  
#### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="6bc75-123">Para crear un contenedor CCW con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6bc75-123">To create a COM callable wrapper using Visual Studio</span></span>  
  
1.  <span data-ttu-id="6bc75-124">Cree un proyecto de biblioteca de clases para la clase administrada que quiera ejecutar en código nativo.</span><span class="sxs-lookup"><span data-stu-id="6bc75-124">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="6bc75-125">La clase debe tener un constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6bc75-125">The class must have a default constructor.</span></span>  
  
     <span data-ttu-id="6bc75-126">Compruebe que dispone de un número de versión de cuatro partes completo para el ensamblado en el archivo AssemblyInfo.</span><span class="sxs-lookup"><span data-stu-id="6bc75-126">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="6bc75-127">Este número es necesario para mantener el control de versiones en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="6bc75-127">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="6bc75-128">Para más información sobre los números de versión, vea [Versiones de los ensamblados](../../../docs/framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="6bc75-128">For more information about version numbers, see [Assembly Versioning](../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
2.  <span data-ttu-id="6bc75-129">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6bc75-129">On the **Project** menu, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6bc75-130">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="6bc75-130">Click the **Compile** tab.</span></span>  
  
4.  <span data-ttu-id="6bc75-131">Active la casilla **Registrar para interoperabilidad COM**.</span><span class="sxs-lookup"><span data-stu-id="6bc75-131">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="6bc75-132">Al compilar el proyecto, el ensamblado se registra automáticamente para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="6bc75-132">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="6bc75-133">Si va a compilar una aplicación nativa en [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], puede usar el ensamblado haciendo clic en **Agregar referencia** en el menú **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6bc75-133">If you are building a native application in [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
#### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="6bc75-134">Para crear un contenedor CCW mediante las herramientas de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6bc75-134">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
-   <span data-ttu-id="6bc75-135">Ejecute la herramienta [Regasm.exe (Herramienta de registro de ensamblados)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md).</span><span class="sxs-lookup"><span data-stu-id="6bc75-135">Run the [Regasm.exe (Assembly Registration Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
 <span data-ttu-id="6bc75-136">Esta herramienta lee los metadatos de ensamblado y agrega las entradas necesarias al Registro.</span><span class="sxs-lookup"><span data-stu-id="6bc75-136">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="6bc75-137">Como resultado, los clientes COM pueden crear clases de .NET Framework de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="6bc75-137">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="6bc75-138">Puede usar el ensamblado como si fuera una clase COM nativa.</span><span class="sxs-lookup"><span data-stu-id="6bc75-138">You can use the assembly as if it were a native COM class.</span></span>  
  
 <span data-ttu-id="6bc75-139">Puede ejecutar Regasm.exe en un ensamblado que se encuentre en cualquier directorio y, después, ejecutar [Gacutil.exe (herramienta de la caché global de ensamblados)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para moverlo a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="6bc75-139">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="6bc75-140">Al mover el ensamblado no se invalidan las entradas del registro de ubicación, porque siempre se examina la caché global de ensamblados si el ensamblado no se encuentra en otra parte.</span><span class="sxs-lookup"><span data-stu-id="6bc75-140">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc75-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bc75-141">See Also</span></span>  
 [<span data-ttu-id="6bc75-142">Contenedor al que se puede llamar en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="6bc75-142">Runtime Callable Wrapper</span></span>](../../../docs/framework/interop/runtime-callable-wrapper.md)  
 [<span data-ttu-id="6bc75-143">Contenedor CCW (COM callable wrapper)</span><span class="sxs-lookup"><span data-stu-id="6bc75-143">COM Callable Wrapper</span></span>](../../../docs/framework/interop/com-callable-wrapper.md)
