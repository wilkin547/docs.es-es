---
title: Procedimiento para configurar componentes COM basados en .NET Framework para la activación sin registro
description: Configure componentes COM basados en .NET para la activación sin registro. El programa de instalación requiere un manifiesto de aplicación de estilo Win32 y un manifiesto de componente .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
ms.openlocfilehash: ffeb342f286663ee7fe733ee617741e0ab30d0d8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282878"
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a><span data-ttu-id="50bb0-104">Procedimiento para configurar componentes COM basados en .NET Framework para la activación sin registro</span><span class="sxs-lookup"><span data-stu-id="50bb0-104">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>

<span data-ttu-id="50bb0-105">La activación sin registro de los componentes de .NET Framework solo es un poco más complicada que la de los componentes COM.</span><span class="sxs-lookup"><span data-stu-id="50bb0-105">Registration-free activation for .NET Framework-based components is only slightly more complicated than it is for COM components.</span></span> <span data-ttu-id="50bb0-106">La configuración requiere dos manifiestos:</span><span class="sxs-lookup"><span data-stu-id="50bb0-106">The setup requires two manifests:</span></span>  
  
- <span data-ttu-id="50bb0-107">Las aplicaciones COM deben tener un manifiesto de aplicación de estilo Win32 para identificar el componente administrado.</span><span class="sxs-lookup"><span data-stu-id="50bb0-107">COM applications must have a Win32-style application manifest to identify the managed component.</span></span>  
  
- <span data-ttu-id="50bb0-108">Los componentes de .NET Framework deben tener un manifiesto de componente con la información de activación que se necesita en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="50bb0-108">.NET Framework-based components must have a component manifest for activation information needed at run time.</span></span>  
  
 <span data-ttu-id="50bb0-109">En este tema se describe cómo asociar un manifiesto de aplicación a una aplicación, cómo asociar un manifiesto de componente a un componente y cómo incrustar un manifiesto de componente en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50bb0-109">This topic describes how to associate an application manifest with an application; associate a component manifest with a component; and embed a component manifest in an assembly.</span></span>  
  
## <a name="create-an-application-manifest"></a><span data-ttu-id="50bb0-110">Creación de un manifiesto de aplicación</span><span class="sxs-lookup"><span data-stu-id="50bb0-110">Create an application manifest</span></span>  
  
1. <span data-ttu-id="50bb0-111">Mediante un editor XML, cree (o modifique) el manifiesto de aplicación propiedad de la aplicación COM que está interoperando con uno o más componentes administrados.</span><span class="sxs-lookup"><span data-stu-id="50bb0-111">Using an XML editor, create (or modify) the application manifest owned by the COM application that is interoperating with one or more managed components.</span></span>  
  
2. <span data-ttu-id="50bb0-112">Inserte el siguiente encabezado estándar al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="50bb0-112">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
    </assembly>
    ```  
  
     <span data-ttu-id="50bb0-113">Para obtener información sobre los elementos del manifiesto y sus atributos, consulte [Manifiestos de aplicación](/windows/desktop/SbsCs/application-manifests).</span><span class="sxs-lookup"><span data-stu-id="50bb0-113">For information about manifest elements and their attributes, see [Application Manifests](/windows/desktop/SbsCs/application-manifests).</span></span>  
  
3. <span data-ttu-id="50bb0-114">Identifique al propietario del manifiesto.</span><span class="sxs-lookup"><span data-stu-id="50bb0-114">Identify the owner of the manifest.</span></span> <span data-ttu-id="50bb0-115">En el ejemplo siguiente, la versión 1 de `myComApp` es el propietario del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="50bb0-115">In the following example, `myComApp` version 1 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myComApp"
                        version="1.0.0.0"
                        processorArchitecture="msil"
      />
    </assembly>  
    ```  
  
4. <span data-ttu-id="50bb0-116">Identifique los ensamblados dependientes.</span><span class="sxs-lookup"><span data-stu-id="50bb0-116">Identify dependent assemblies.</span></span> <span data-ttu-id="50bb0-117">En el ejemplo siguiente, `myComApp` depende de `myManagedComp`.</span><span class="sxs-lookup"><span data-stu-id="50bb0-117">In the following example, `myComApp` depends on `myManagedComp`.</span></span>  
  
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
  
5. <span data-ttu-id="50bb0-118">Nombre el archivo de manifiesto y guárdelo.</span><span class="sxs-lookup"><span data-stu-id="50bb0-118">Save and name the manifest file.</span></span> <span data-ttu-id="50bb0-119">El nombre de un manifiesto de aplicación es el nombre del ensamblado ejecutable seguido de la extensión .manifest.</span><span class="sxs-lookup"><span data-stu-id="50bb0-119">The name of an application manifest is the name of the assembly executable followed by the .manifest extension.</span></span> <span data-ttu-id="50bb0-120">Por ejemplo, el nombre del archivo de manifiesto de la aplicación de myComApp.exe es myComApp.exe.manifest.</span><span class="sxs-lookup"><span data-stu-id="50bb0-120">For example, the application manifest file name for myComApp.exe is myComApp.exe.manifest.</span></span>  
  
<span data-ttu-id="50bb0-121">El manifiesto de aplicación se puede instalar en el mismo directorio que la aplicación COM.</span><span class="sxs-lookup"><span data-stu-id="50bb0-121">You can install an application manifest in the same directory as the COM application.</span></span> <span data-ttu-id="50bb0-122">Opcionalmente, se puede agregar como recurso al archivo .exe de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="50bb0-122">Alternatively, you can add it as a resource to the application's .exe file.</span></span> <span data-ttu-id="50bb0-123">Para más información, vea [Acerca de los ensamblados en paralelo](/windows/desktop/SbsCs/about-side-by-side-assemblies-).</span><span class="sxs-lookup"><span data-stu-id="50bb0-123">For more information, see [About Side-by-Side Assemblies](/windows/desktop/SbsCs/about-side-by-side-assemblies-).</span></span>  
  
## <a name="create-a-component-manifest"></a><span data-ttu-id="50bb0-124">Creación de un manifiesto de componente</span><span class="sxs-lookup"><span data-stu-id="50bb0-124">Create a component manifest</span></span>  
  
1. <span data-ttu-id="50bb0-125">Mediante un editor XML, cree un manifiesto de componente para describir el ensamblado administrado.</span><span class="sxs-lookup"><span data-stu-id="50bb0-125">Using an XML editor, create a component manifest to describe the managed assembly.</span></span>  
  
2. <span data-ttu-id="50bb0-126">Inserte el siguiente encabezado estándar al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="50bb0-126">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
    </assembly>
    ```  
  
3. <span data-ttu-id="50bb0-127">Identifique al propietario del archivo.</span><span class="sxs-lookup"><span data-stu-id="50bb0-127">Identify the owner of the file.</span></span> <span data-ttu-id="50bb0-128">El elemento `<assemblyIdentity>` del elemento `<dependentAssembly>` del archivo del manifiesto de aplicación debe coincidir con el del manifiesto del componente.</span><span class="sxs-lookup"><span data-stu-id="50bb0-128">The `<assemblyIdentity>` element of the `<dependentAssembly>` element in application manifest file must match the one in the component manifest.</span></span> <span data-ttu-id="50bb0-129">En el ejemplo siguiente, la versión 1.2.3.4 de `myManagedComp` es el propietario del archivo de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="50bb0-129">In the following example, `myManagedComp` version 1.2.3.4 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />
    </assembly>
    ```  
  
4. <span data-ttu-id="50bb0-130">Identifique cada clase del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50bb0-130">Identify each class in the assembly.</span></span> <span data-ttu-id="50bb0-131">Use el elemento `<clrClass>` para identificar cada clase del ensamblado administrado de manera única.</span><span class="sxs-lookup"><span data-stu-id="50bb0-131">Use the `<clrClass>` element to uniquely identify each class in the managed assembly.</span></span> <span data-ttu-id="50bb0-132">El elemento, que es un subelemento del elemento `<assembly>`, tiene los atributos que se describen en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="50bb0-132">The element, which is a subelement of the `<assembly>` element, has the attributes described in the following table.</span></span>  
  
    |<span data-ttu-id="50bb0-133">Atributo</span><span class="sxs-lookup"><span data-stu-id="50bb0-133">Attribute</span></span>|<span data-ttu-id="50bb0-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="50bb0-134">Description</span></span>|<span data-ttu-id="50bb0-135">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="50bb0-135">Required</span></span>|  
    |---------------|-----------------|--------------|  
    |`clsid`|<span data-ttu-id="50bb0-136">El identificador que especifica la clase que ha de ser activada.</span><span class="sxs-lookup"><span data-stu-id="50bb0-136">The identifier that specifies the class to be activated.</span></span>|<span data-ttu-id="50bb0-137">Sí</span><span class="sxs-lookup"><span data-stu-id="50bb0-137">Yes</span></span>|  
    |`description`|<span data-ttu-id="50bb0-138">Cadena que informa al usuario sobre el componente.</span><span class="sxs-lookup"><span data-stu-id="50bb0-138">A string that informs the user about the component.</span></span> <span data-ttu-id="50bb0-139">De manera predeterminada, es una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="50bb0-139">An empty string is the default.</span></span>|<span data-ttu-id="50bb0-140">No</span><span class="sxs-lookup"><span data-stu-id="50bb0-140">No</span></span>|  
    |`name`|<span data-ttu-id="50bb0-141">Cadena que representa la clase administrada.</span><span class="sxs-lookup"><span data-stu-id="50bb0-141">A string that represents the managed class.</span></span>|<span data-ttu-id="50bb0-142">Sí</span><span class="sxs-lookup"><span data-stu-id="50bb0-142">Yes</span></span>|  
    |`progid`|<span data-ttu-id="50bb0-143">Identificador que hay que usar para la activación del enlace en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="50bb0-143">The identifier to be used for late-bound activation.</span></span>|<span data-ttu-id="50bb0-144">No</span><span class="sxs-lookup"><span data-stu-id="50bb0-144">No</span></span>|  
    |`threadingModel`|<span data-ttu-id="50bb0-145">Modelo de subprocesos COM.</span><span class="sxs-lookup"><span data-stu-id="50bb0-145">The COM threading model.</span></span> <span data-ttu-id="50bb0-146">El valor predeterminado es "Both".</span><span class="sxs-lookup"><span data-stu-id="50bb0-146">"Both" is the default value.</span></span>|<span data-ttu-id="50bb0-147">No</span><span class="sxs-lookup"><span data-stu-id="50bb0-147">No</span></span>|  
    |`runtimeVersion`|<span data-ttu-id="50bb0-148">Especifica la versión de Common Language Runtime (CLR) que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="50bb0-148">Specifies the common language runtime (CLR) version to use.</span></span> <span data-ttu-id="50bb0-149">Si no especifica este atributo y el CLR aún no se ha cargado, el componente se cargará con la última versión de CLR instalada antes de la versión 4.</span><span class="sxs-lookup"><span data-stu-id="50bb0-149">If you do not specify this attribute, and the CLR is not already loaded, the component is loaded with the latest installed CLR prior to CLR version 4.</span></span> <span data-ttu-id="50bb0-150">Si especifica v1.0.3705, v1.1.4322 o v2.0.50727, la versión se actualizará automáticamente a la última versión de CLR instalada antes de la versión version 4 (normalmente, v2.0.50727).</span><span class="sxs-lookup"><span data-stu-id="50bb0-150">If you specify v1.0.3705, v1.1.4322, or v2.0.50727, the version automatically rolls forward to the latest installed CLR version prior to CLR version 4 (usually v2.0.50727).</span></span> <span data-ttu-id="50bb0-151">Si ya se ha cargado otra versión de CLR y la versión especificada se puede cargar en paralelo y en el mismo proceso, se cargará la versión especificada; de lo contrario, se usará la versión de CLR ya cargada.</span><span class="sxs-lookup"><span data-stu-id="50bb0-151">If another version of the CLR is already loaded and the specified version can be loaded side-by-side in-process, the specified version is loaded; otherwise, the loaded CLR is used.</span></span> <span data-ttu-id="50bb0-152">Esto puede dar lugar a un error de carga.</span><span class="sxs-lookup"><span data-stu-id="50bb0-152">This might cause a load failure.</span></span>|<span data-ttu-id="50bb0-153">No</span><span class="sxs-lookup"><span data-stu-id="50bb0-153">No</span></span>|  
    |`tlbid`|<span data-ttu-id="50bb0-154">Identificador de la biblioteca de tipos que contiene información de tipos sobre la clase.</span><span class="sxs-lookup"><span data-stu-id="50bb0-154">The identifier of the type library that contains type information about the class.</span></span>|<span data-ttu-id="50bb0-155">No</span><span class="sxs-lookup"><span data-stu-id="50bb0-155">No</span></span>|  
  
     <span data-ttu-id="50bb0-156">Todos los atributos distinguen mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="50bb0-156">All attribute tags are case-sensitive.</span></span> <span data-ttu-id="50bb0-157">Se pueden obtener los CLSID, ProgIDs, modelos de subprocesos y la versión del motor en tiempo de ejecución visualizando la biblioteca de tipos exportada para el ensamblado con OLE/COM ObjectViewer (Oleview.exe).</span><span class="sxs-lookup"><span data-stu-id="50bb0-157">You can obtain CLSIDs, ProgIDs, threading models, and the runtime version by viewing the exported type library for the assembly with the OLE/COM ObjectViewer (Oleview.exe).</span></span>  
  
     <span data-ttu-id="50bb0-158">El siguiente manifiesto de componente identifica dos clases, `testClass1` y `testClass2`.</span><span class="sxs-lookup"><span data-stu-id="50bb0-158">The following component manifest identifies two classes, `testClass1` and `testClass2`.</span></span>  
  
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
  
5. <span data-ttu-id="50bb0-159">Nombre el archivo de manifiesto y guárdelo.</span><span class="sxs-lookup"><span data-stu-id="50bb0-159">Save and name the manifest file.</span></span> <span data-ttu-id="50bb0-160">El nombre de un manifiesto de componente es el nombre de la biblioteca de ensamblados seguido de la extensión .manifest.</span><span class="sxs-lookup"><span data-stu-id="50bb0-160">The name of a component manifest is the name of the assembly library followed by the .manifest extension.</span></span> <span data-ttu-id="50bb0-161">Por ejemplo, myManagedComp.dll es myManagedComp.manifest.</span><span class="sxs-lookup"><span data-stu-id="50bb0-161">For example, the myManagedComp.dll is myManagedComp.manifest.</span></span>  
  
 <span data-ttu-id="50bb0-162">Es necesario incrustar el manifiesto de componente como recurso en el ensamblado</span><span class="sxs-lookup"><span data-stu-id="50bb0-162">You must embed the component manifest as a resource in the assembly.</span></span>  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a><span data-ttu-id="50bb0-163">Para incrustar un manifiesto de componente en un ensamblado administrado</span><span class="sxs-lookup"><span data-stu-id="50bb0-163">To embed a component manifest in a managed assembly</span></span>  
  
1. <span data-ttu-id="50bb0-164">Cree un script de recursos que contenga la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="50bb0-164">Create a resource script that contains the following statement:</span></span>  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     <span data-ttu-id="50bb0-165">En esta instrucción, `myManagedComp.manifest` es el nombre del manifiesto de componente que se incrusta.</span><span class="sxs-lookup"><span data-stu-id="50bb0-165">In this statement, `myManagedComp.manifest` is the name of the component manifest being embedded.</span></span> <span data-ttu-id="50bb0-166">En este ejemplo, el archivo de script se denomina `myresource.rc`.</span><span class="sxs-lookup"><span data-stu-id="50bb0-166">For this example, the script file name is `myresource.rc`.</span></span>  
  
2. <span data-ttu-id="50bb0-167">Compile el script mediante el compilador de recursos de Microsoft Windows (Rc.exe).</span><span class="sxs-lookup"><span data-stu-id="50bb0-167">Compile the script using the Microsoft Windows Resource Compiler (Rc.exe).</span></span> <span data-ttu-id="50bb0-168">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="50bb0-168">At the command prompt, type the following command:</span></span>  
  
     `rc myresource.rc`  
  
     <span data-ttu-id="50bb0-169">Rc.exe produce el archivo de recursos `myresource.res`.</span><span class="sxs-lookup"><span data-stu-id="50bb0-169">Rc.exe produces the `myresource.res` resource file.</span></span>  
  
3. <span data-ttu-id="50bb0-170">Compile de nuevo el archivo de origen del ensamblado y especifique el archivo de recursos mediante la opción **/win32res**:</span><span class="sxs-lookup"><span data-stu-id="50bb0-170">Compile the assembly's source file again and specify the resource file by using the **/win32res** option:</span></span>  
  
    `/win32res:myresource.res`  
  
     <span data-ttu-id="50bb0-171">Una vez más, `myresource.res` es el nombre del archivo de recursos que contiene los recursos incrustados.</span><span class="sxs-lookup"><span data-stu-id="50bb0-171">Again, `myresource.res` is the name of the resource file containing embedded resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50bb0-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="50bb0-172">See also</span></span>

- [<span data-ttu-id="50bb0-173">Interoperabilidad COM sin registro</span><span class="sxs-lookup"><span data-stu-id="50bb0-173">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)
- <span data-ttu-id="50bb0-174">[Requisitos para interoperabilidad COM sin registro](/previous-versions/dotnet/netframework-4.0/f8h7012w(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="50bb0-174">[Requirements for Registration-Free COM Interop](/previous-versions/dotnet/netframework-4.0/f8h7012w(v=vs.100))</span></span>
- <span data-ttu-id="50bb0-175">[Configuración de componentes COM para la activación sin registro](/previous-versions/dotnet/netframework-4.0/x65a421a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="50bb0-175">[Configuring COM Components for Registration-Free Activation](/previous-versions/dotnet/netframework-4.0/x65a421a(v=vs.100))</span></span>
- <span data-ttu-id="50bb0-176">[Registration-Free Activation of .NET-Based Components: A Walkthrough](/previous-versions/dotnet/articles/ms973915(v=msdn.10)) (Tutorial: Activación sin registro de componentes basados en .NET)</span><span class="sxs-lookup"><span data-stu-id="50bb0-176">[Registration-Free Activation of .NET-Based Components: A Walkthrough](/previous-versions/dotnet/articles/ms973915(v=msdn.10))</span></span>
