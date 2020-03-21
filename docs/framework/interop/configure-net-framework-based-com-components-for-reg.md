---
title: 'Cómo: Configurar componentes COM basados en .NET Framework para la activación sin registro'
ms.date: 03/30/2017
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
ms.openlocfilehash: dedf5ab51ab5cf9befb5bd183968388406df4e5b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181462"
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a><span data-ttu-id="59783-102">Cómo: Configurar componentes COM basados en .NET Framework para la activación sin registro</span><span class="sxs-lookup"><span data-stu-id="59783-102">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>
<span data-ttu-id="59783-103">La activación sin registro de los componentes de .NET Framework solo es un poco más complicada que la de los componentes COM.</span><span class="sxs-lookup"><span data-stu-id="59783-103">Registration-free activation for .NET Framework-based components is only slightly more complicated than it is for COM components.</span></span> <span data-ttu-id="59783-104">La configuración requiere dos manifiestos:</span><span class="sxs-lookup"><span data-stu-id="59783-104">The setup requires two manifests:</span></span>  
  
- <span data-ttu-id="59783-105">Las aplicaciones COM deben tener un manifiesto de aplicación de estilo Win32 para identificar el componente administrado.</span><span class="sxs-lookup"><span data-stu-id="59783-105">COM applications must have a Win32-style application manifest to identify the managed component.</span></span>  
  
- <span data-ttu-id="59783-106">Los componentes de .NET Framework deben tener un manifiesto de componente con la información de activación que se necesita en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="59783-106">.NET Framework-based components must have a component manifest for activation information needed at run time.</span></span>  
  
 <span data-ttu-id="59783-107">En este tema se describe cómo asociar un manifiesto de aplicación a una aplicación, cómo asociar un manifiesto de componente a un componente y cómo incrustar un manifiesto de componente en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="59783-107">This topic describes how to associate an application manifest with an application; associate a component manifest with a component; and embed a component manifest in an assembly.</span></span>  
  
### <a name="to-create-an-application-manifest"></a><span data-ttu-id="59783-108">Para crear un manifiesto de aplicación</span><span class="sxs-lookup"><span data-stu-id="59783-108">To create an application manifest</span></span>  
  
1. <span data-ttu-id="59783-109">Mediante un editor XML, cree (o modifique) el manifiesto de aplicación propiedad de la aplicación COM que está interoperando con uno o más componentes administrados.</span><span class="sxs-lookup"><span data-stu-id="59783-109">Using an XML editor, create (or modify) the application manifest owned by the COM application that is interoperating with one or more managed components.</span></span>  
  
2. <span data-ttu-id="59783-110">Inserte el siguiente encabezado estándar al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="59783-110">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     <span data-ttu-id="59783-111">Para obtener información sobre los elementos del manifiesto y sus atributos, consulte [Manifiestos de aplicación](/windows/desktop/SbsCs/application-manifests).</span><span class="sxs-lookup"><span data-stu-id="59783-111">For information about manifest elements and their attributes, see [Application Manifests](/windows/desktop/SbsCs/application-manifests).</span></span>  
  
3. <span data-ttu-id="59783-112">Identifique al propietario del manifiesto.</span><span class="sxs-lookup"><span data-stu-id="59783-112">Identify the owner of the manifest.</span></span> <span data-ttu-id="59783-113">En el ejemplo siguiente, la versión 1 de `myComApp` es el propietario del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="59783-113">In the following example, `myComApp` version 1 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myComApp"
                        version="1.0.0.0"
                        processorArchitecture="msil"
      />  
    ```  
  
4. <span data-ttu-id="59783-114">Identifique los ensamblados dependientes.</span><span class="sxs-lookup"><span data-stu-id="59783-114">Identify dependent assemblies.</span></span> <span data-ttu-id="59783-115">En el ejemplo siguiente, `myComApp` depende de `myManagedComp`.</span><span class="sxs-lookup"><span data-stu-id="59783-115">In the following example, `myComApp` depends on `myManagedComp`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myComApp"
                        version="1.0.0.0"
                        processorArchitecture="x86"
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myManagedComp"
                        version="6.0.0.0"
                        processorArchitecture="X86"
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5. <span data-ttu-id="59783-116">Nombre el archivo de manifiesto y guárdelo.</span><span class="sxs-lookup"><span data-stu-id="59783-116">Save and name the manifest file.</span></span> <span data-ttu-id="59783-117">El nombre de un manifiesto de aplicación es el nombre del ensamblado ejecutable seguido de la extensión .manifest.</span><span class="sxs-lookup"><span data-stu-id="59783-117">The name of an application manifest is the name of the assembly executable followed by the .manifest extension.</span></span> <span data-ttu-id="59783-118">Por ejemplo, el nombre del archivo de manifiesto de la aplicación de myComApp.exe es myComApp.exe.manifest.</span><span class="sxs-lookup"><span data-stu-id="59783-118">For example, the application manifest file name for myComApp.exe is myComApp.exe.manifest.</span></span>  
  
 <span data-ttu-id="59783-119">El manifiesto de aplicación se puede instalar en el mismo directorio que la aplicación COM.</span><span class="sxs-lookup"><span data-stu-id="59783-119">You can install an application manifest in the same directory as the COM application.</span></span> <span data-ttu-id="59783-120">Opcionalmente, se puede agregar como recurso al archivo .exe de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59783-120">Alternatively, you can add it as a resource to the application's .exe file.</span></span> <span data-ttu-id="59783-121">Para más información, consulte el artículo sobre [los ensamblados en paralelo](/windows/desktop/SbsCs/about-side-by-side-assemblies-).</span><span class="sxs-lookup"><span data-stu-id="59783-121">For additional information, For more information, see [About Side-by-Side Assemblies](/windows/desktop/SbsCs/about-side-by-side-assemblies-).</span></span>  
  
#### <a name="to-create-a-component-manifest"></a><span data-ttu-id="59783-122">Para crear un manifiesto de componente</span><span class="sxs-lookup"><span data-stu-id="59783-122">To create a component manifest</span></span>  
  
1. <span data-ttu-id="59783-123">Mediante un editor XML, cree un manifiesto de componente para describir el ensamblado administrado.</span><span class="sxs-lookup"><span data-stu-id="59783-123">Using an XML editor, create a component manifest to describe the managed assembly.</span></span>  
  
2. <span data-ttu-id="59783-124">Inserte el siguiente encabezado estándar al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="59783-124">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3. <span data-ttu-id="59783-125">Identifique al propietario del archivo.</span><span class="sxs-lookup"><span data-stu-id="59783-125">Identify the owner of the file.</span></span> <span data-ttu-id="59783-126">El elemento `<assemblyIdentity>` del elemento `<dependentAssembly>` del archivo del manifiesto de aplicación debe coincidir con el del manifiesto del componente.</span><span class="sxs-lookup"><span data-stu-id="59783-126">The `<assemblyIdentity>` element of the `<dependentAssembly>` element in application manifest file must match the one in the component manifest.</span></span> <span data-ttu-id="59783-127">En el ejemplo siguiente, la versión 1.2.3.4 de `myManagedComp` es el propietario del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="59783-127">In the following example, `myManagedComp` version 1.2.3.4 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4. <span data-ttu-id="59783-128">Identifique cada clase del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="59783-128">Identify each class in the assembly.</span></span> <span data-ttu-id="59783-129">Use el elemento `<clrClass>` para identificar cada clase del ensamblado administrado de manera única.</span><span class="sxs-lookup"><span data-stu-id="59783-129">Use the `<clrClass>` element to uniquely identify each class in the managed assembly.</span></span> <span data-ttu-id="59783-130">El elemento, que es un subelemento del elemento `<assembly>`, tiene los atributos que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="59783-130">The element, which is a subelement of the `<assembly>` element, has the attributes described in the following table.</span></span>  
  
    |<span data-ttu-id="59783-131">Atributo</span><span class="sxs-lookup"><span data-stu-id="59783-131">Attribute</span></span>|<span data-ttu-id="59783-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="59783-132">Description</span></span>|<span data-ttu-id="59783-133">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="59783-133">Required</span></span>|  
    |---------------|-----------------|--------------|  
    |`clsid`|<span data-ttu-id="59783-134">El identificador que especifica la clase que ha de ser activada.</span><span class="sxs-lookup"><span data-stu-id="59783-134">The identifier that specifies the class to be activated.</span></span>|<span data-ttu-id="59783-135">Sí</span><span class="sxs-lookup"><span data-stu-id="59783-135">Yes</span></span>|  
    |`description`|<span data-ttu-id="59783-136">Cadena que informa al usuario sobre el componente.</span><span class="sxs-lookup"><span data-stu-id="59783-136">A string that informs the user about the component.</span></span> <span data-ttu-id="59783-137">De manera predeterminada, es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="59783-137">An empty string is the default.</span></span>|<span data-ttu-id="59783-138">Sin </span><span class="sxs-lookup"><span data-stu-id="59783-138">No</span></span>|  
    |`name`|<span data-ttu-id="59783-139">Cadena que representa la clase administrada.</span><span class="sxs-lookup"><span data-stu-id="59783-139">A string that represents the managed class.</span></span>|<span data-ttu-id="59783-140">Sí</span><span class="sxs-lookup"><span data-stu-id="59783-140">Yes</span></span>|  
    |`progid`|<span data-ttu-id="59783-141">Identificador que hay que usar para la activación del enlace en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="59783-141">The identifier to be used for late-bound activation.</span></span>|<span data-ttu-id="59783-142">Sin </span><span class="sxs-lookup"><span data-stu-id="59783-142">No</span></span>|  
    |`threadingModel`|<span data-ttu-id="59783-143">Modelo de subprocesos COM.</span><span class="sxs-lookup"><span data-stu-id="59783-143">The COM threading model.</span></span> <span data-ttu-id="59783-144">El valor predeterminado es "Both".</span><span class="sxs-lookup"><span data-stu-id="59783-144">"Both" is the default value.</span></span>|<span data-ttu-id="59783-145">Sin </span><span class="sxs-lookup"><span data-stu-id="59783-145">No</span></span>|  
    |`runtimeVersion`|<span data-ttu-id="59783-146">Especifica la versión de Common Language Runtime (CLR) que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="59783-146">Specifies the common language runtime (CLR) version to use.</span></span> <span data-ttu-id="59783-147">Si no especifica este atributo y el CLR aún no se ha cargado, el componente se cargará con la última versión de CLR instalada antes de la versión 4.</span><span class="sxs-lookup"><span data-stu-id="59783-147">If you do not specify this attribute, and the CLR is not already loaded, the component is loaded with the latest installed CLR prior to CLR version 4.</span></span> <span data-ttu-id="59783-148">Si especifica v1.0.3705, v1.1.4322 o v2.0.50727, la versión se actualizará automáticamente a la última versión de CLR instalada antes de la versión version 4 (normalmente, v2.0.50727).</span><span class="sxs-lookup"><span data-stu-id="59783-148">If you specify v1.0.3705, v1.1.4322, or v2.0.50727, the version automatically rolls forward to the latest installed CLR version prior to CLR version 4 (usually v2.0.50727).</span></span> <span data-ttu-id="59783-149">Si ya se ha cargado otra versión de CLR y la versión especificada se puede cargar en paralelo y en el mismo proceso, se cargará la versión especificada; de lo contrario, se usará la versión de CLR ya cargada.</span><span class="sxs-lookup"><span data-stu-id="59783-149">If another version of the CLR is already loaded and the specified version can be loaded side-by-side in-process, the specified version is loaded; otherwise, the loaded CLR is used.</span></span> <span data-ttu-id="59783-150">Esto puede dar lugar a un error de carga.</span><span class="sxs-lookup"><span data-stu-id="59783-150">This might cause a load failure.</span></span>|<span data-ttu-id="59783-151">Sin </span><span class="sxs-lookup"><span data-stu-id="59783-151">No</span></span>|  
    |`tlbid`|<span data-ttu-id="59783-152">Identificador de la biblioteca de tipos que contiene información de tipos sobre la clase.</span><span class="sxs-lookup"><span data-stu-id="59783-152">The identifier of the type library that contains type information about the class.</span></span>|<span data-ttu-id="59783-153">Sin </span><span class="sxs-lookup"><span data-stu-id="59783-153">No</span></span>|  
  
     <span data-ttu-id="59783-154">Todos los atributos distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="59783-154">All attribute tags are case-sensitive.</span></span> <span data-ttu-id="59783-155">Se pueden obtener los CLSID, ProgIDs, modelos de subprocesos y la versión del motor en tiempo de ejecución visualizando la biblioteca de tipos exportada para el ensamblado con OLE/COM ObjectViewer (Oleview.exe).</span><span class="sxs-lookup"><span data-stu-id="59783-155">You can obtain CLSIDs, ProgIDs, threading models, and the runtime version by viewing the exported type library for the assembly with the OLE/COM ObjectViewer (Oleview.exe).</span></span>  
  
     <span data-ttu-id="59783-156">El siguiente manifiesto de componente identifica dos clases, `testClass1` y `testClass2`.</span><span class="sxs-lookup"><span data-stu-id="59783-156">The following component manifest identifies two classes, `testClass1` and `testClass2`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5. <span data-ttu-id="59783-157">Nombre el archivo de manifiesto y guárdelo.</span><span class="sxs-lookup"><span data-stu-id="59783-157">Save and name the manifest file.</span></span> <span data-ttu-id="59783-158">El nombre de un manifiesto de componente es el nombre de la biblioteca de ensamblados seguido de la extensión .manifest.</span><span class="sxs-lookup"><span data-stu-id="59783-158">The name of a component manifest is the name of the assembly library followed by the .manifest extension.</span></span> <span data-ttu-id="59783-159">Por ejemplo, myManagedComp.dll es myManagedComp.manifest.</span><span class="sxs-lookup"><span data-stu-id="59783-159">For example, the myManagedComp.dll is myManagedComp.manifest.</span></span>  
  
 <span data-ttu-id="59783-160">Es necesario incrustar el manifiesto de componente como recurso en el ensamblado</span><span class="sxs-lookup"><span data-stu-id="59783-160">You must embed the component manifest as a resource in the assembly.</span></span>  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a><span data-ttu-id="59783-161">Para incrustar un manifiesto de componente en un ensamblado administrado</span><span class="sxs-lookup"><span data-stu-id="59783-161">To embed a component manifest in a managed assembly</span></span>  
  
1. <span data-ttu-id="59783-162">Cree un script de recursos que contenga la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="59783-162">Create a resource script that contains the following statement:</span></span>  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     <span data-ttu-id="59783-163">En esta instrucción, `myManagedComp.manifest` es el nombre del manifiesto de componente que se incrusta.</span><span class="sxs-lookup"><span data-stu-id="59783-163">In this statement, `myManagedComp.manifest` is the name of the component manifest being embedded.</span></span> <span data-ttu-id="59783-164">En este ejemplo, el archivo de script se denomina `myresource.rc`.</span><span class="sxs-lookup"><span data-stu-id="59783-164">For this example, the script file name is `myresource.rc`.</span></span>  
  
2. <span data-ttu-id="59783-165">Compile el script mediante el compilador de recursos de Microsoft Windows (Rc.exe).</span><span class="sxs-lookup"><span data-stu-id="59783-165">Compile the script using the Microsoft Windows Resource Compiler (Rc.exe).</span></span> <span data-ttu-id="59783-166">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="59783-166">At the command prompt, type the following command:</span></span>  
  
     `rc myresource.rc`  
  
     <span data-ttu-id="59783-167">Rc.exe produce el archivo de recursos `myresource.res`.</span><span class="sxs-lookup"><span data-stu-id="59783-167">Rc.exe produces the `myresource.res` resource file.</span></span>  
  
3. <span data-ttu-id="59783-168">Compile de nuevo el archivo de origen del ensamblado y especifique el archivo de recursos mediante la opción **/win32res**:</span><span class="sxs-lookup"><span data-stu-id="59783-168">Compile the assembly's source file again and specify the resource file by using the **/win32res** option:</span></span>  
  
    `/win32res:myresource.res`  
  
     <span data-ttu-id="59783-169">Una vez más, `myresource.res` es el nombre del archivo de recursos que contiene los recursos incrustados.</span><span class="sxs-lookup"><span data-stu-id="59783-169">Again, `myresource.res` is the name of the resource file containing embedded resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59783-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59783-170">See also</span></span>

- [<span data-ttu-id="59783-171">Interoperabilidad COM sin registro</span><span class="sxs-lookup"><span data-stu-id="59783-171">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)
- <span data-ttu-id="59783-172">[Requisitos para interoperabilidad COM sin registro](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f8h7012w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="59783-172">[Requirements for Registration-Free COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f8h7012w(v=vs.100))</span></span>
- <span data-ttu-id="59783-173">[Configuración de componentes COM para la activación sin registro](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x65a421a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="59783-173">[Configuring COM Components for Registration-Free Activation](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x65a421a(v=vs.100))</span></span>
- <span data-ttu-id="59783-174">[Registration-Free Activation of .NET-Based Components: A Walkthrough](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973915(v=msdn.10)) (Tutorial: Activación sin registro de componentes basados en .NET)</span><span class="sxs-lookup"><span data-stu-id="59783-174">[Registration-Free Activation of .NET-Based Components: A Walkthrough](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973915(v=msdn.10))</span></span>
