---
description: 'Más información acerca de cómo: registrar y configurar un moniker de servicio'
title: Procedimiento para registrar y configurar un moniker de servicio
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: 9c6867941a5b96c6ced0f8e371e10697144bd121
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643467"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a><span data-ttu-id="cb11c-103">Procedimiento para registrar y configurar un moniker de servicio</span><span class="sxs-lookup"><span data-stu-id="cb11c-103">How to: Register and Configure a Service Moniker</span></span>

<span data-ttu-id="cb11c-104">Antes de utilizar el moniker del servicio Windows Communication Foundation (WCF) dentro de una aplicación COM con un contrato con tipo, debe registrar los tipos con atributos necesarios en COM y configurar la aplicación COM y el moniker con la configuración de enlace necesaria.</span><span class="sxs-lookup"><span data-stu-id="cb11c-104">Before using the Windows Communication Foundation (WCF) service moniker within a COM application with a typed contract, you must register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>

## <a name="register-the-required-attributed-types-with-com"></a><span data-ttu-id="cb11c-105">Registrar los tipos con atributos necesarios con COM</span><span class="sxs-lookup"><span data-stu-id="cb11c-105">Register the required attributed types with COM</span></span>

1. <span data-ttu-id="cb11c-106">Use la herramienta de [utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) para recuperar el contrato de metadatos del servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="cb11c-106">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) tool to retrieve the metadata contract from the WCF service.</span></span> <span data-ttu-id="cb11c-107">Esto genera el código fuente para un ensamblado de cliente de WCF y un archivo de configuración de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="cb11c-107">This generates the source code for a WCF client assembly and a client application configuration file.</span></span>

2. <span data-ttu-id="cb11c-108">Asegúrese de que los tipos del ensamblado se marcan como `ComVisible`.</span><span class="sxs-lookup"><span data-stu-id="cb11c-108">Ensure that the types in the assembly are marked as `ComVisible`.</span></span> <span data-ttu-id="cb11c-109">Para ello, agregue el siguiente atributo al archivo *AssemblyInfo.CS* en el proyecto de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cb11c-109">To do so, add the following attribute to the *AssemblyInfo.cs* file in your Visual Studio project.</span></span>

    ```csharp
    [assembly: ComVisible(true)]
    ```

3. <span data-ttu-id="cb11c-110">Compile el cliente WCF administrado como un ensamblado con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="cb11c-110">Compile the managed WCF client as a strong-named assembly.</span></span> <span data-ttu-id="cb11c-111">Para ello se es necesario firmar con un par de claves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="cb11c-111">This requires signing with a cryptographic key pair.</span></span> <span data-ttu-id="cb11c-112">Para obtener más información, vea [Procedimiento para firmar un ensamblado con un nombre seguro](../../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="cb11c-112">For more information, see [Signing an Assembly with a Strong Name](../../../standard/assembly/sign-strong-name.md).</span></span>

4. <span data-ttu-id="cb11c-113">Utilice la herramienta de registro de ensamblados (Regasm.exe) con la opción `-tlb` para registrar los tipos del ensamblado en COM.</span><span class="sxs-lookup"><span data-stu-id="cb11c-113">Use the Assembly Registration (Regasm.exe) tool with the `-tlb` option to register the types in the assembly with COM.</span></span>

5. <span data-ttu-id="cb11c-114">Use la herramienta de la caché global de ensamblados (Gacutil.exe) para agregar el ensamblado a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="cb11c-114">Use the Global Assembly Cache (Gacutil.exe) tool to add the assembly to the global assembly cache.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb11c-115">Firmar y agregar el ensamblado a la caché global de ensamblados son pasos opcionales, pero permiten simplificar el proceso de carga del ensamblado desde la ubicación correcta en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cb11c-115">Signing the assembly and adding it to the Global Assembly Cache are optional steps, but they can simplify the process of loading the assembly from the correct location at runtime.</span></span>

## <a name="configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a><span data-ttu-id="cb11c-116">Configurar la aplicación COM y el moniker con la configuración de enlace necesaria</span><span class="sxs-lookup"><span data-stu-id="cb11c-116">Configure the COM application and the moniker with the required binding configuration</span></span>

- <span data-ttu-id="cb11c-117">Coloque las definiciones de enlace (generadas por la [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) en el archivo de configuración de la aplicación cliente generada en el archivo de configuración de la aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="cb11c-117">Place the binding definitions (generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) in the generated client application configuration file) in the client application's configuration file.</span></span> <span data-ttu-id="cb11c-118">Por ejemplo, para un ejecutable de Visual Basic 6.0 denominado CallCenterClient.exe, la configuración debe encontrarse en un archivo denominado CallCenterConfig.exe.config en el mismo directorio que la aplicación ejecutable.</span><span class="sxs-lookup"><span data-stu-id="cb11c-118">For example, for a Visual Basic 6.0 executable named CallCenterClient.exe, the configuration should be placed in a file named CallCenterConfig.exe.config within the same directory as the executable.</span></span> <span data-ttu-id="cb11c-119">De este modo la aplicación cliente puede utilizar el moniker.</span><span class="sxs-lookup"><span data-stu-id="cb11c-119">The client application can now use the moniker.</span></span> <span data-ttu-id="cb11c-120">Tenga en cuenta que la configuración de enlace no es necesaria si se usa uno de los tipos de enlace estándar que proporciona WCF.</span><span class="sxs-lookup"><span data-stu-id="cb11c-120">Note that the binding configuration is not required if using one of the standard binding types provided by WCF.</span></span>

     <span data-ttu-id="cb11c-121">El siguiente tipo está registrado:</span><span class="sxs-lookup"><span data-stu-id="cb11c-121">The following type is registered.</span></span>

    ```csharp
    using System.ServiceModel;

    [ServiceContract]
    public interface IMathService
    {
        [OperationContract]
        public int Add(int x, int y);
        [OperationContract]
        public int Subtract(int x, int y);
    }
    ```

     <span data-ttu-id="cb11c-122">La aplicación se expone mediante un enlace `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="cb11c-122">The application is exposed using a `wsHttpBinding` binding.</span></span> <span data-ttu-id="cb11c-123">Para el tipo y configuración de aplicación especificados, se utilizan las siguientes cadenas moniker de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cb11c-123">For the given type and application configuration, the following example moniker strings are used.</span></span>

    ```
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1
    ```

     <span data-ttu-id="cb11c-124">o bien</span><span class="sxs-lookup"><span data-stu-id="cb11c-124">or</span></span>

    ```
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}
    ```

     <span data-ttu-id="cb11c-125">Puede utilizar cualquiera de estas cadenas moniker desde una aplicación de Visual Basic 6.0, siempre que agregue una referencia al ensamblado que contiene los tipos `IMathService`, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cb11c-125">You can use either of these moniker strings from within a Visual Basic 6.0 application, after adding a reference to the assembly that contains the `IMathService` types, as shown in the following sample code.</span></span>

    ```vb
    Dim mathProxy As IMathService
    Dim result As Integer

    Set mathProxy = GetObject( _
            "service4:address=http://localhost/MathService, _
            binding=wsHttpBinding, _
            bindingConfiguration=Binding1")

    result = mathProxy.Add(3, 5)
    ```

     <span data-ttu-id="cb11c-126">En este ejemplo, la definición de la configuración de enlace `Binding1` se almacena en un archivo de configuración con un nombre adecuado para la aplicación cliente, como *vb6appname.exe.config*.</span><span class="sxs-lookup"><span data-stu-id="cb11c-126">In this example, the definition for the binding configuration `Binding1` is stored in a suitably named configuration file for the client application, such as *vb6appname.exe.config*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb11c-127">Puede utilizar un código similar en una aplicación C#, C++, o cualquier otra aplicación de lenguaje .NET.</span><span class="sxs-lookup"><span data-stu-id="cb11c-127">You can use similar code in a C#, a C++, or any other .NET Language application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cb11c-128">Si el moniker tiene un formato incorrecto o si el servicio no está disponible, la llamada a `GetObject` devuelve un error de "sintaxis no válida".</span><span class="sxs-lookup"><span data-stu-id="cb11c-128">If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error of "Invalid Syntax".</span></span> <span data-ttu-id="cb11c-129">Si recibe este error, asegúrese de que el moniker que está utilizando es correcto y el servicio está disponible.</span><span class="sxs-lookup"><span data-stu-id="cb11c-129">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>

     <span data-ttu-id="cb11c-130">Aunque este tema se centra en el uso del moniker de servicio de Visual Basic Código 6,0, se puede utilizar un moniker de servicio de otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="cb11c-130">Although this topic focuses on using the service moniker from Visual Basic 6.0 code, you can use a service moniker from other languages.</span></span> <span data-ttu-id="cb11c-131">Si utiliza un moniker del código de C++, deberá importar el ensamblado generado por Svcutil.exe con "no_namespace named_guids raw_interfaces_only", como se muestra en el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="cb11c-131">When using a moniker from C++ code the Svcutil.exe generated assembly should be imported with "no_namespace named_guids raw_interfaces_only" as shown in the following code.</span></span>

    ```cpp
    #import "ComTestProxy.tlb" no_namespace named_guids
    ```

     <span data-ttu-id="cb11c-132">De este modo se modifican las definiciones de la interfaz importada para que todos los métodos devuelvan `HResult`.</span><span class="sxs-lookup"><span data-stu-id="cb11c-132">This modifies the imported interface definitions so that all methods return an `HResult`.</span></span> <span data-ttu-id="cb11c-133">Cualquier otro valor devuelto se convierte en parámetros de salida.</span><span class="sxs-lookup"><span data-stu-id="cb11c-133">Any other return values are converted into out parameters.</span></span> <span data-ttu-id="cb11c-134">La ejecución global de los métodos sigue siendo la misma.</span><span class="sxs-lookup"><span data-stu-id="cb11c-134">The overall execution of the methods remains the same.</span></span> <span data-ttu-id="cb11c-135">Esto permite determinar la causa de una excepción al llamar a un método en el proxy.</span><span class="sxs-lookup"><span data-stu-id="cb11c-135">This allows you to determine the cause of an exception when calling a method on the proxy.</span></span> <span data-ttu-id="cb11c-136">Esta funcionalidad sólo está disponible en el código de C++.</span><span class="sxs-lookup"><span data-stu-id="cb11c-136">This functionality is only available from C++ code.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb11c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb11c-137">See also</span></span>

- [<span data-ttu-id="cb11c-138">Herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="cb11c-138">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
