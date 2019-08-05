---
title: Procedimiento para crear contenedores COM
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4ae9710b99c85cfcbe3de2669c7ee85d0d24ef4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629342"
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="3395b-102">Procedimiento para crear contenedores COM</span><span class="sxs-lookup"><span data-stu-id="3395b-102">How to: Create COM Wrappers</span></span>

<span data-ttu-id="3395b-103">Puede crear contenedores del Modelo de objetos componentes (COM) mediante características de Visual Studio 2005 o las herramientas Tlbimp.exe y Regasm.exe de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3395b-103">You can create Component Object Model (COM) wrappers by using Visual Studio 2005 features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="3395b-104">Ambos métodos generan dos tipos de contenedores COM:</span><span class="sxs-lookup"><span data-stu-id="3395b-104">Both methods generate two types of COM wrappers:</span></span>

- <span data-ttu-id="3395b-105">Un [contenedor RCW](../../../docs/standard/native-interop/runtime-callable-wrapper.md) desde una biblioteca de tipos para ejecutar un objeto COM en código administrado.</span><span class="sxs-lookup"><span data-stu-id="3395b-105">A [Runtime Callable Wrapper](../../../docs/standard/native-interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>

- <span data-ttu-id="3395b-106">Un [contenedor CCW](../../../docs/standard/native-interop/com-callable-wrapper.md) con la configuración del Registro necesaria para ejecutar un objeto administrado en una aplicación nativa.</span><span class="sxs-lookup"><span data-stu-id="3395b-106">A [COM Callable Wrapper](../../../docs/standard/native-interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>

<span data-ttu-id="3395b-107">En Visual Studio 2005, puede agregar el contenedor COM como una referencia al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3395b-107">In Visual Studio 2005, you can add the COM wrapper as a reference to your project.</span></span>

## <a name="wrap-com-objects-in-a-managed-application"></a><span data-ttu-id="3395b-108">Encapsulado de objetos COM en una aplicación administrada</span><span class="sxs-lookup"><span data-stu-id="3395b-108">Wrap COM Objects in a Managed Application</span></span>

### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="3395b-109">Para crear un contenedor RCW con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3395b-109">To create a runtime callable wrapper using Visual Studio</span></span>

1. <span data-ttu-id="3395b-110">Abra el proyecto de la aplicación administrada.</span><span class="sxs-lookup"><span data-stu-id="3395b-110">Open the project for your managed application.</span></span>

2. <span data-ttu-id="3395b-111">En el menú **Proyecto**, haga clic en **Mostrar todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="3395b-111">On the **Project** menu, click **Show All Files**.</span></span>

3. <span data-ttu-id="3395b-112">En el menú **Proyecto**, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="3395b-112">On the **Project** menu, click **Add Reference**.</span></span>

4. <span data-ttu-id="3395b-113">En el cuadro de diálogo Agregar referencia, haga clic en la pestaña **COM**, seleccione el componente que quiera usar y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3395b-113">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>

     <span data-ttu-id="3395b-114">En el **Explorador de soluciones**, tenga en cuenta que el componente COM se agrega a la carpeta Referencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3395b-114">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>

<span data-ttu-id="3395b-115">Ahora puede escribir código para tener acceso al objeto COM.</span><span class="sxs-lookup"><span data-stu-id="3395b-115">You can now write code to access the COM object.</span></span> <span data-ttu-id="3395b-116">Puede empezar por declarar el objeto, como, por ejemplo, con una instrucción `Imports` para Visual Basic o una instrucción `Using` para C#.</span><span class="sxs-lookup"><span data-stu-id="3395b-116">You can begin by declaring the object, such as with an `Imports` statement for Visual Basic or a `Using` statement for C#.</span></span>

> [!NOTE]
> <span data-ttu-id="3395b-117">Si quiere programar componentes de Microsoft Office, instale primero los [ensamblados de interoperabilidad primarios de Microsoft Office](https://go.microsoft.com/fwlink/?LinkId=50479) (PIA) desde el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3395b-117">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies](https://go.microsoft.com/fwlink/?LinkId=50479) (PIAs) from the Microsoft Download Center.</span></span> <span data-ttu-id="3395b-118">En el paso 4, seleccione la versión más reciente de la biblioteca de objetos disponible para el producto de Office que quiere, como la **biblioteca de objetos de Microsoft Word 11.0**.</span><span class="sxs-lookup"><span data-stu-id="3395b-118">In step 4, select the latest version of the object library available for the Office product you want, such as the **Microsoft Word 11.0 Object Library**.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="3395b-119">Para crear un contenedor RCW mediante las herramientas de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3395b-119">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
- <span data-ttu-id="3395b-120">Ejecute la herramienta [TlbImp.exe (Importador de la biblioteca de tipos)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md).</span><span class="sxs-lookup"><span data-stu-id="3395b-120">Run the [Tlbimp.exe (Type Library Importer)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="3395b-121">Esta herramienta crea un ensamblado que contiene los metadatos de tiempo de ejecución para los tipos definidos en la biblioteca de tipos original.</span><span class="sxs-lookup"><span data-stu-id="3395b-121">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrap-managed-objects-in-a-native-application"></a><span data-ttu-id="3395b-122">Encapsulado de objetos administrados en una aplicación nativa</span><span class="sxs-lookup"><span data-stu-id="3395b-122">Wrap Managed Objects in a Native Application</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="3395b-123">Para crear un contenedor CCW con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3395b-123">To create a COM callable wrapper using Visual Studio</span></span>  
  
1. <span data-ttu-id="3395b-124">Cree un proyecto de biblioteca de clases para la clase administrada que quiera ejecutar en código nativo.</span><span class="sxs-lookup"><span data-stu-id="3395b-124">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="3395b-125">La clase debe tener un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="3395b-125">The class must have a parameterless constructor.</span></span>  
  
     <span data-ttu-id="3395b-126">Compruebe que dispone de un número de versión de cuatro partes completo para el ensamblado en el archivo AssemblyInfo.</span><span class="sxs-lookup"><span data-stu-id="3395b-126">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="3395b-127">Este número es necesario para mantener el control de versiones en el Registro de Windows.</span><span class="sxs-lookup"><span data-stu-id="3395b-127">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="3395b-128">Para más información sobre los números de versión, vea [Versiones de los ensamblados](../../../docs/framework/app-domains/assembly-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="3395b-128">For more information about version numbers, see [Assembly Versioning](../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
2. <span data-ttu-id="3395b-129">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3395b-129">On the **Project** menu, click **Properties**.</span></span>  
  
3. <span data-ttu-id="3395b-130">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="3395b-130">Click the **Compile** tab.</span></span>  
  
4. <span data-ttu-id="3395b-131">Active la casilla **Registrar para interoperabilidad COM**.</span><span class="sxs-lookup"><span data-stu-id="3395b-131">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="3395b-132">Al compilar el proyecto, el ensamblado se registra automáticamente para la interoperabilidad COM.</span><span class="sxs-lookup"><span data-stu-id="3395b-132">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="3395b-133">Si va a compilar una aplicación nativa en Visual Studio 2005, puede usar el ensamblado haciendo clic en **Agregar referencia** en el menú **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="3395b-133">If you are building a native application in Visual Studio 2005, you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="3395b-134">Para crear un contenedor CCW mediante las herramientas de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3395b-134">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
<span data-ttu-id="3395b-135">Ejecute la herramienta [Regasm.exe (Herramienta de registro de ensamblados)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md).</span><span class="sxs-lookup"><span data-stu-id="3395b-135">Run the [Regasm.exe (Assembly Registration Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
<span data-ttu-id="3395b-136">Esta herramienta lee los metadatos de ensamblado y agrega las entradas necesarias al Registro.</span><span class="sxs-lookup"><span data-stu-id="3395b-136">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="3395b-137">Como resultado, los clientes COM pueden crear clases de .NET Framework de forma transparente.</span><span class="sxs-lookup"><span data-stu-id="3395b-137">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="3395b-138">Puede usar el ensamblado como si fuera una clase COM nativa.</span><span class="sxs-lookup"><span data-stu-id="3395b-138">You can use the assembly as if it were a native COM class.</span></span>  
  
<span data-ttu-id="3395b-139">Puede ejecutar Regasm.exe en un ensamblado que se encuentre en cualquier directorio y, después, ejecutar [Gacutil.exe (herramienta de la caché global de ensamblados)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) para moverlo a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="3395b-139">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="3395b-140">Al mover el ensamblado no se invalidan las entradas del registro de ubicación, porque siempre se examina la caché global de ensamblados si el ensamblado no se encuentra en otra parte.</span><span class="sxs-lookup"><span data-stu-id="3395b-140">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3395b-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="3395b-141">See also</span></span>

- [<span data-ttu-id="3395b-142">Contenedor al que se puede llamar en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3395b-142">Runtime Callable Wrapper</span></span>](../../../docs/standard/native-interop/runtime-callable-wrapper.md)
- [<span data-ttu-id="3395b-143">Contenedor CCW (COM callable wrapper)</span><span class="sxs-lookup"><span data-stu-id="3395b-143">COM Callable Wrapper</span></span>](../../../docs/standard/native-interop/com-callable-wrapper.md)
