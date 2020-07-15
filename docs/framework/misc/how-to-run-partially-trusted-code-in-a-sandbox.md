---
title: 'Cómo: Ejecutar código de confianza parcial en un recinto'
description: Descubra cómo ejecutar código de confianza parcial en un espacio aislado en .NET. La clase AppDomain es una manera eficaz de recintos de las aplicaciones administradas.
ms.date: 03/30/2017
helpviewer_keywords:
- partially trusted code
- sandboxing
- partial trust
- restricted security environment
- code security, sandboxing
ms.assetid: d1ad722b-5b49-4040-bff3-431b94bb8095
ms.openlocfilehash: e02b5d679fb1f5947373399ac1226732623ef96d
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309240"
---
# <a name="how-to-run-partially-trusted-code-in-a-sandbox"></a><span data-ttu-id="92874-104">Cómo: Ejecutar código de confianza parcial en un recinto</span><span class="sxs-lookup"><span data-stu-id="92874-104">How to: Run Partially Trusted Code in a Sandbox</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="92874-105">El uso de espacios aislados consiste en ejecutar código en un entorno de seguridad restringido que limita los permisos de acceso concedidos al código.</span><span class="sxs-lookup"><span data-stu-id="92874-105">Sandboxing is the practice of running code in a restricted security environment, which limits the access permissions granted to the code.</span></span> <span data-ttu-id="92874-106">Por ejemplo, si tiene una biblioteca administrada procedente de un origen en el que no confía plenamente, no la ejecute como si fuese de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="92874-106">For example, if you have a managed library from a source you do not completely trust, you should not run it as fully trusted.</span></span> <span data-ttu-id="92874-107">En su lugar, coloque el código en un espacio aislado que limite los permisos a los que considere necesarios (por ejemplo, el permiso <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>).</span><span class="sxs-lookup"><span data-stu-id="92874-107">Instead, you should place the code in a sandbox that limits its permissions to those that you expect it to need (for example, <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission).</span></span>  
  
 <span data-ttu-id="92874-108">También puede usar el espacio aislado para probar el código que va a distribuir y que se ejecutará en entornos de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="92874-108">You can also use sandboxing to test code you will be distributing that will run in partially trusted environments.</span></span>  
  
 <span data-ttu-id="92874-109"><xref:System.AppDomain> es una forma eficaz de proporcionar un espacio aislado para las aplicaciones administradas.</span><span class="sxs-lookup"><span data-stu-id="92874-109">An <xref:System.AppDomain> is an effective way of providing a sandbox for managed applications.</span></span> <span data-ttu-id="92874-110">Los dominios de aplicación que se usan para ejecutar código de confianza parcial tienen permisos que definen los recursos protegidos que están disponibles cuando se ejecuta dentro de ese <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="92874-110">Application domains that are used for running partially trusted code have permissions that define the protected resources that are available when running within that <xref:System.AppDomain>.</span></span> <span data-ttu-id="92874-111">El código que se ejecuta dentro de <xref:System.AppDomain> está limitado por los permisos asociados a <xref:System.AppDomain> y tan solo puede tener acceso a los recursos especificados.</span><span class="sxs-lookup"><span data-stu-id="92874-111">Code that runs inside the <xref:System.AppDomain> is bound by the permissions associated with the <xref:System.AppDomain> and is allowed to access only the specified resources.</span></span> <span data-ttu-id="92874-112"><xref:System.AppDomain> también incluye una matriz <xref:System.Security.Policy.StrongName> que se usa para identificar los ensamblados que cargan con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="92874-112">The <xref:System.AppDomain> also includes a <xref:System.Security.Policy.StrongName> array that is used to identify assemblies that are to be loaded as fully trusted.</span></span> <span data-ttu-id="92874-113">Esto permite que el creador de un <xref:System.AppDomain> inicie un nuevo dominio en espacio aislado que permita confiar plenamente en ensamblados del asistente concretos.</span><span class="sxs-lookup"><span data-stu-id="92874-113">This enables the creator of an <xref:System.AppDomain> to start a new sandboxed domain that allows specific helper assemblies to be fully trusted.</span></span> <span data-ttu-id="92874-114">Otra opción para cargar ensamblados como de plena confianza es colocarlos en la caché de ensamblados global. Sin embargo, eso cargará los ensamblados con plena confianza en todos los dominios de aplicación creados en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="92874-114">Another option for loading assemblies as fully trusted is to place them in the global assembly cache; however, that will load assemblies as fully trusted in all application domains created on that computer.</span></span> <span data-ttu-id="92874-115">La lista de nombres seguros admite una decisión por <xref:System.AppDomain> que proporciona una determinación más restrictiva.</span><span class="sxs-lookup"><span data-stu-id="92874-115">The list of strong names supports a per-<xref:System.AppDomain> decision that provides more restrictive determination.</span></span>  
  
 <span data-ttu-id="92874-116">La sobrecarga del método <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> se puede usar para especificar el conjunto de permisos para las aplicaciones que se ejecutan en un espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="92874-116">You can use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> method overload to specify the permission set for applications that run in a sandbox.</span></span> <span data-ttu-id="92874-117">Esta sobrecarga permite especificar el nivel exacto de seguridad de acceso del código que se desea.</span><span class="sxs-lookup"><span data-stu-id="92874-117">This overload enables you to specify the exact level of code access security you want.</span></span> <span data-ttu-id="92874-118">Los ensamblados que se cargan en <xref:System.AppDomain> mediante esta sobrecarga pueden tener únicamente el conjunto de permisos especificado o pueden ser de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="92874-118">Assemblies that are loaded into an <xref:System.AppDomain> by using this overload can either have the specified grant set only, or can be fully trusted.</span></span> <span data-ttu-id="92874-119">Si el ensamblado está en la caché global de ensamblados o aparece enumerado en el parámetro de matrices `fullTrustAssemblies` (<xref:System.Security.Policy.StrongName>), se le concede confianza plena.</span><span class="sxs-lookup"><span data-stu-id="92874-119">The assembly is granted full trust if it is in the global assembly cache or listed in the `fullTrustAssemblies` (the <xref:System.Security.Policy.StrongName>) array parameter.</span></span> <span data-ttu-id="92874-120">Tan solo deben agregarse a la lista `fullTrustAssemblies` los ensamblados que se sabe que son de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="92874-120">Only assemblies known to be fully trusted should be added to the `fullTrustAssemblies` list.</span></span>  
  
 <span data-ttu-id="92874-121">La sobrecarga tiene la siguiente firma:</span><span class="sxs-lookup"><span data-stu-id="92874-121">The overload has the following signature:</span></span>  
  
```csharp
AppDomain.CreateDomain( string friendlyName,  
                        Evidence securityInfo,  
                        AppDomainSetup info,  
                        PermissionSet grantSet,  
                        params StrongName[] fullTrustAssemblies);  
```  
  
 <span data-ttu-id="92874-122">Los parámetros de la sobrecarga del método <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> especifican el nombre de <xref:System.AppDomain>, la evidencia de <xref:System.AppDomain>, el objeto <xref:System.AppDomainSetup> que identifica la base de la aplicación para el espacio aislado, el conjunto de permisos que se va a usar y los nombres seguros para los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="92874-122">The parameters for the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> method overload specify the name of the <xref:System.AppDomain>, the evidence for the <xref:System.AppDomain>, the <xref:System.AppDomainSetup> object that identifies the application base for the sandbox, the permission set to use, and the strong names for fully trusted assemblies.</span></span>  
  
 <span data-ttu-id="92874-123">Por motivos de seguridad, la base de la aplicación especificada en el parámetro `info` no debe ser la base de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="92874-123">For security reasons, the application base specified in the `info` parameter should not be the application base for the hosting application.</span></span>  
  
 <span data-ttu-id="92874-124">Para el parámetro `grantSet`, puede especificar un conjunto de permisos que haya creado explícitamente o un conjunto de permisos estándar conjunto creado mediante el método <xref:System.Security.SecurityManager.GetStandardSandbox%2A>.</span><span class="sxs-lookup"><span data-stu-id="92874-124">For the `grantSet` parameter, you can specify either a permission set you have explicitly created, or a standard permission set created by the <xref:System.Security.SecurityManager.GetStandardSandbox%2A> method.</span></span>  
  
 <span data-ttu-id="92874-125">A diferencia de la mayoría de cargas de <xref:System.AppDomain>, la evidencia para <xref:System.AppDomain> (proporcionado por el parámetro `securityInfo`) no se usa para determinar el conjunto de permisos de los ensamblados de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="92874-125">Unlike most <xref:System.AppDomain> loads, the evidence for the <xref:System.AppDomain> (which is provided by the `securityInfo` parameter) is not used to determine the grant set for the partially trusted assemblies.</span></span> <span data-ttu-id="92874-126">En su lugar, se especifica por separado mediante el parámetro `grantSet`.</span><span class="sxs-lookup"><span data-stu-id="92874-126">Instead, it is independently specified by the `grantSet` parameter.</span></span> <span data-ttu-id="92874-127">Sin embargo, la evidencia puede usarse para otros fines como determinar el ámbito de almacenamiento aislado.</span><span class="sxs-lookup"><span data-stu-id="92874-127">However, the evidence can be used for other purposes such as determining the isolated storage scope.</span></span>  
  
### <a name="to-run-an-application-in-a-sandbox"></a><span data-ttu-id="92874-128">Para ejecutar una aplicación en un espacio aislado</span><span class="sxs-lookup"><span data-stu-id="92874-128">To run an application in a sandbox</span></span>  
  
1. <span data-ttu-id="92874-129">Cree el conjunto de permisos que se concederán a la aplicación no confiable.</span><span class="sxs-lookup"><span data-stu-id="92874-129">Create the permission set to be granted to the untrusted application.</span></span> <span data-ttu-id="92874-130">El permiso mínimo que se puede conceder es <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>.</span><span class="sxs-lookup"><span data-stu-id="92874-130">The minimum permission you can grant is <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission.</span></span> <span data-ttu-id="92874-131">También puede conceder permisos adicionales si piensa que son seguros para el código no seguro, por ejemplo, <xref:System.Security.Permissions.IsolatedStorageFilePermission>.</span><span class="sxs-lookup"><span data-stu-id="92874-131">You can also grant additional permissions you think might be safe for untrusted code; for example, <xref:System.Security.Permissions.IsolatedStorageFilePermission>.</span></span> <span data-ttu-id="92874-132">El siguiente código crea un nuevo conjunto de permisos que contiene únicamente el permiso <xref:System.Security.Permissions.SecurityPermissionFlag.Execution>.</span><span class="sxs-lookup"><span data-stu-id="92874-132">The following code creates a new permission set with only <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission.</span></span>  
  
    ```csharp
    PermissionSet permSet = new PermissionSet(PermissionState.None);  
    permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
    ```  
  
     <span data-ttu-id="92874-133">Si lo prefiere, puede usar un conjunto de permisos con nombre existente, como Internet.</span><span class="sxs-lookup"><span data-stu-id="92874-133">Alternatively, you can use an existing named permission set, such as Internet.</span></span>  
  
    ```csharp
    Evidence ev = new Evidence();  
    ev.AddHostEvidence(new Zone(SecurityZone.Internet));  
    PermissionSet internetPS = SecurityManager.GetStandardSandbox(ev);  
    ```  
  
     <span data-ttu-id="92874-134">El método <xref:System.Security.SecurityManager.GetStandardSandbox%2A> devolverá un conjunto de permisos `Internet` o un conjunto de permisos `LocalIntranet` según la zona de la evidencia.</span><span class="sxs-lookup"><span data-stu-id="92874-134">The <xref:System.Security.SecurityManager.GetStandardSandbox%2A> method returns either an `Internet` permission set or a `LocalIntranet` permission set depending on the zone in the evidence.</span></span> <span data-ttu-id="92874-135"><xref:System.Security.SecurityManager.GetStandardSandbox%2A> también construye permisos de identidad para algunos de los objetos de evidencia que se pasan como referencias.</span><span class="sxs-lookup"><span data-stu-id="92874-135"><xref:System.Security.SecurityManager.GetStandardSandbox%2A> also constructs identity permissions for some of the evidence objects passed as references.</span></span>  
  
2. <span data-ttu-id="92874-136">Firme el ensamblado que contiene la clase host (denominada `Sandboxer` en este ejemplo) que llama al código de confianza.</span><span class="sxs-lookup"><span data-stu-id="92874-136">Sign the assembly that contains the hosting class (named `Sandboxer` in this example) that calls the untrusted code.</span></span> <span data-ttu-id="92874-137">Agregue el <xref:System.Security.Policy.StrongName> usado para firmar el ensamblado a la matriz <xref:System.Security.Policy.StrongName> del parámetro `fullTrustAssemblies` de la llamada <xref:System.AppDomain.CreateDomain%2A>.</span><span class="sxs-lookup"><span data-stu-id="92874-137">Add the <xref:System.Security.Policy.StrongName> used to sign the assembly to the <xref:System.Security.Policy.StrongName> array of the `fullTrustAssemblies` parameter of the <xref:System.AppDomain.CreateDomain%2A> call.</span></span> <span data-ttu-id="92874-138">La clase host debe ejecutarse como de plena confianza para habilitar la ejecución del código de confianza parcial u ofrecer servicios a la aplicación de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="92874-138">The hosting class must run as fully trusted to enable the execution of the partial-trust code or to offer services to the partial-trust application.</span></span> <span data-ttu-id="92874-139">Así es como se lee el <xref:System.Security.Policy.StrongName> de un ensamblado:</span><span class="sxs-lookup"><span data-stu-id="92874-139">This is how you read the <xref:System.Security.Policy.StrongName> of an assembly:</span></span>  
  
    ```csharp
    StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
    ```  
  
     <span data-ttu-id="92874-140">Los ensamblados de .NET Framework como mscorlib y System.dll no tienen que agregarse a la lista de plena confianza porque se cargan como de plena confianza desde la caché de ensamblados global.</span><span class="sxs-lookup"><span data-stu-id="92874-140">.NET Framework assemblies such as mscorlib and System.dll do not have to be added to the full-trust list because they are loaded as fully trusted from the global assembly cache.</span></span>  
  
3. <span data-ttu-id="92874-141">Inicialice el parámetro <xref:System.AppDomainSetup> del método <xref:System.AppDomain.CreateDomain%2A>.</span><span class="sxs-lookup"><span data-stu-id="92874-141">Initialize the <xref:System.AppDomainSetup> parameter of the <xref:System.AppDomain.CreateDomain%2A> method.</span></span> <span data-ttu-id="92874-142">Con este parámetro, puede controlar muchas de las opciones del nuevo <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="92874-142">With this parameter, you can control many of the settings of the new <xref:System.AppDomain>.</span></span> <span data-ttu-id="92874-143">La propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> es un valor importante y debe ser diferente de la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> para el <xref:System.AppDomain> de la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="92874-143">The <xref:System.AppDomainSetup.ApplicationBase%2A> property is an important setting, and should be different from the <xref:System.AppDomainSetup.ApplicationBase%2A> property for the <xref:System.AppDomain> of the hosting application.</span></span> <span data-ttu-id="92874-144">Si los valores de <xref:System.AppDomainSetup.ApplicationBase%2A> son iguales, la aplicación de confianza parcial puede hacer que la aplicación host cargue (como de plena confianza) una excepción que define y, por tanto, aprovecharse de ella.</span><span class="sxs-lookup"><span data-stu-id="92874-144">If the <xref:System.AppDomainSetup.ApplicationBase%2A> settings are the same, the partial-trust application can get the hosting application to load (as fully trusted) an exception it defines, thus exploiting it.</span></span> <span data-ttu-id="92874-145">Este es otro motivo por el que no se recomienda un bloque catch (excepción).</span><span class="sxs-lookup"><span data-stu-id="92874-145">This is another reason why a catch (exception) is not recommended.</span></span> <span data-ttu-id="92874-146">El riesgo de ataques se reduce si la base de la aplicación del host y la base de la aplicación de la aplicación en espacio aislado se configuran de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="92874-146">Setting the application base of the host differently from the application base of the sandboxed application mitigates the risk of exploits.</span></span>  
  
    ```csharp
    AppDomainSetup adSetup = new AppDomainSetup();  
    adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
    ```  
  
4. <span data-ttu-id="92874-147">Llame a la sobrecarga del método <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> para crear el dominio de aplicación usando los parámetros especificados.</span><span class="sxs-lookup"><span data-stu-id="92874-147">Call the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> method overload to create the application domain using the parameters we have specified.</span></span>  
  
     <span data-ttu-id="92874-148">La firma de este método es:</span><span class="sxs-lookup"><span data-stu-id="92874-148">The signature for this method is:</span></span>  
  
    ```csharp
    public static AppDomain CreateDomain(string friendlyName,
        Evidence securityInfo, AppDomainSetup info, PermissionSet grantSet,
        params StrongName[] fullTrustAssemblies)  
    ```  
  
     <span data-ttu-id="92874-149">Información adicional:</span><span class="sxs-lookup"><span data-stu-id="92874-149">Additional information:</span></span>  
  
    - <span data-ttu-id="92874-150">Esta es la única sobrecarga del método <xref:System.AppDomain.CreateDomain%2A> que toma <xref:System.Security.PermissionSet> como un parámetro y, por lo tanto, la única sobrecarga que permite cargar una aplicación en un entorno de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="92874-150">This is the only overload of the <xref:System.AppDomain.CreateDomain%2A> method that takes a <xref:System.Security.PermissionSet> as a parameter, and thus the only overload that lets you load an application in a partial-trust setting.</span></span>  
  
    - <span data-ttu-id="92874-151">El parámetro `evidence` no se usa para calcular un conjunto de permisos, sino que se usa para identificar otras características de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="92874-151">The `evidence` parameter is not used to calculate a permission set; it is used for identification by other features of the .NET Framework.</span></span>  
  
    - <span data-ttu-id="92874-152">En esta sobrecarga es obligatorio establecer la propiedad <xref:System.AppDomainSetup.ApplicationBase%2A> del parámetro `info`.</span><span class="sxs-lookup"><span data-stu-id="92874-152">Setting the <xref:System.AppDomainSetup.ApplicationBase%2A> property of the `info` parameter is mandatory for this overload.</span></span>  
  
    - <span data-ttu-id="92874-153">El parámetro `fullTrustAssemblies` tiene la palabra clave `params`, lo que significa que no es necesario crear una matriz <xref:System.Security.Policy.StrongName>.</span><span class="sxs-lookup"><span data-stu-id="92874-153">The `fullTrustAssemblies` parameter has the `params` keyword, which means that it is not necessary to create a <xref:System.Security.Policy.StrongName> array.</span></span> <span data-ttu-id="92874-154">Se permite pasar 0, 1 o más nombres seguros como parámetros.</span><span class="sxs-lookup"><span data-stu-id="92874-154">Passing 0, 1, or more strong names as parameters is allowed.</span></span>  
  
    - <span data-ttu-id="92874-155">El código para crear el dominio de aplicación es:</span><span class="sxs-lookup"><span data-stu-id="92874-155">The code to create the application domain is:</span></span>  
  
    ```csharp
    AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
    ```  
  
5. <span data-ttu-id="92874-156">Cargar el código en el espacio aislado <xref:System.AppDomain> que creó.</span><span class="sxs-lookup"><span data-stu-id="92874-156">Load the code into the sandboxing <xref:System.AppDomain> that you created.</span></span> <span data-ttu-id="92874-157">Esto puede hacerse de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="92874-157">This can be done in two ways:</span></span>  
  
    - <span data-ttu-id="92874-158">Llame al método <xref:System.AppDomain.ExecuteAssembly%2A> para el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="92874-158">Call the <xref:System.AppDomain.ExecuteAssembly%2A> method for the assembly.</span></span>  
  
    - <span data-ttu-id="92874-159">Use el método <xref:System.Activator.CreateInstanceFrom%2A> para crear una instancia de una clase derivada de <xref:System.MarshalByRefObject> en el nuevo <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="92874-159">Use the <xref:System.Activator.CreateInstanceFrom%2A> method to create an instance of a class derived from <xref:System.MarshalByRefObject> in the new <xref:System.AppDomain>.</span></span>  
  
     <span data-ttu-id="92874-160">El segundo método es preferible, porque es más fácil pasar parámetros a la nueva instancia <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="92874-160">The second method is preferable, because it makes it easier to pass parameters to the new <xref:System.AppDomain> instance.</span></span> <span data-ttu-id="92874-161">El método <xref:System.Activator.CreateInstanceFrom%2A> proporciona dos características importantes:</span><span class="sxs-lookup"><span data-stu-id="92874-161">The <xref:System.Activator.CreateInstanceFrom%2A> method provides two important features:</span></span>  
  
    - <span data-ttu-id="92874-162">Puede usar una base de código que apunte a una ubicación que no contenga su ensamblado.</span><span class="sxs-lookup"><span data-stu-id="92874-162">You can use a code base that points to a location that does not contain your assembly.</span></span>  
  
    - <span data-ttu-id="92874-163">Puede realizar la creación en un <xref:System.Security.CodeAccessPermission.Assert%2A> de plena confianza (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>), lo que le permite crear una instancia de una clase crítica.</span><span class="sxs-lookup"><span data-stu-id="92874-163">You can do the creation under an <xref:System.Security.CodeAccessPermission.Assert%2A> for full-trust (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>), which enables you to create an instance of a critical class.</span></span> <span data-ttu-id="92874-164">(Esto sucede cuando el ensamblado no tiene marcas de transparencia y se carga como de plena confianza). Por lo tanto, debe tener cuidado de crear solo código en el que confíe con esta función y se recomienda crear solo instancias de clases de plena confianza en el nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="92874-164">(This happens whenever your assembly has no transparency markings and is loaded as fully trusted.) Therefore, you have to be careful to create only code that you trust with this function, and we recommend that you create only instances of fully trusted classes in the new application domain.</span></span>  
  
    ```csharp
    ObjectHandle handle = Activator.CreateInstanceFrom(  
    newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
           typeof(Sandboxer).FullName );  
    ```  
  
     <span data-ttu-id="92874-165">Para crear una instancia de una clase en un dominio nuevo, la clase debe extender la <xref:System.MarshalByRefObject> clase.</span><span class="sxs-lookup"><span data-stu-id="92874-165">To create an instance of a class in a new domain, the class must extend the <xref:System.MarshalByRefObject> class.</span></span>
  
    ```csharp
    class Sandboxer:MarshalByRefObject  
    ```  
  
6. <span data-ttu-id="92874-166">Desempaquete la nueva instancia del dominio en una referencia en este dominio.</span><span class="sxs-lookup"><span data-stu-id="92874-166">Unwrap the new domain instance into a reference in this domain.</span></span> <span data-ttu-id="92874-167">Esta referencia se usa para ejecutar el código no confiable.</span><span class="sxs-lookup"><span data-stu-id="92874-167">This reference is used to execute the untrusted code.</span></span>  
  
    ```csharp
    Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
    ```  
  
7. <span data-ttu-id="92874-168">Llame al método `ExecuteUntrustedCode` en la instancia de la clase `Sandboxer` que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="92874-168">Call the `ExecuteUntrustedCode` method in the instance of the `Sandboxer` class you just created.</span></span>  
  
    ```csharp
    newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    ```  
  
     <span data-ttu-id="92874-169">Esta llamada se ejecuta en el dominio de la aplicación en espacio aislado, que tiene permisos restringidos.</span><span class="sxs-lookup"><span data-stu-id="92874-169">This call is executed in the sandboxed application domain, which has restricted permissions.</span></span>  
  
    ```csharp
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the entry point in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            // Invoke the method.  
            target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
        //When information is obtained from a SecurityException extra information is provided if it is
        //accessed in full-trust.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
    ```  
  
     <span data-ttu-id="92874-170"><xref:System.Reflection> se usa para obtener el identificador de un método en el ensamblado de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="92874-170"><xref:System.Reflection> is used to get a handle of a method in the partially trusted assembly.</span></span> <span data-ttu-id="92874-171">El identificador puede usarse para ejecutar código de forma segura con permisos mínimos.</span><span class="sxs-lookup"><span data-stu-id="92874-171">The handle can be used to execute code in a safe way with minimum permissions.</span></span>  
  
     <span data-ttu-id="92874-172">En el código anterior, observe <xref:System.Security.PermissionSet.Assert%2A> para el permiso de plena confianza antes de imprimir <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="92874-172">In the previous code, note the <xref:System.Security.PermissionSet.Assert%2A> for the full-trust permission before printing the <xref:System.Security.SecurityException>.</span></span>  
  
    ```csharp
    new PermissionSet(PermissionState.Unrestricted).Assert()  
    ```  
  
     <span data-ttu-id="92874-173">La aserción de plena confianza se usa para obtener la información ampliada de <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="92874-173">The full-trust assert is used to obtain extended information from the <xref:System.Security.SecurityException>.</span></span> <span data-ttu-id="92874-174">Sin <xref:System.Security.PermissionSet.Assert%2A>, el método <xref:System.Security.SecurityException.ToString%2A> de <xref:System.Security.SecurityException> detectará que hay código de confianza parcial en la pila y restringirá la información devuelta.</span><span class="sxs-lookup"><span data-stu-id="92874-174">Without the <xref:System.Security.PermissionSet.Assert%2A>, the <xref:System.Security.SecurityException.ToString%2A> method of <xref:System.Security.SecurityException> will discover that there is partially trusted code on the stack and will restrict the information returned.</span></span> <span data-ttu-id="92874-175">Esto podría provocar problemas de seguridad si el código de confianza parcial llega a leer esa información, pero el riesgo se mitiga al no conceder <xref:System.Security.Permissions.UIPermission>.</span><span class="sxs-lookup"><span data-stu-id="92874-175">This could cause security issues if the partial-trust code could read that information, but the risk is mitigated by not granting <xref:System.Security.Permissions.UIPermission>.</span></span> <span data-ttu-id="92874-176">La aserción de plena confianza debe usarse con moderación y solo cuando si se está seguro de que no se permite al código de confianza parcial elevarse a plena confianza.</span><span class="sxs-lookup"><span data-stu-id="92874-176">The full-trust assert should be used sparingly and only when you are sure that you are not allowing partial-trust code to elevate to full trust.</span></span> <span data-ttu-id="92874-177">Como norma general, no llame a un código en el que no confía en la misma función y tras invocar una aserción de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="92874-177">As a rule, do not call code you do not trust in the same function and after you called an assert for full trust.</span></span> <span data-ttu-id="92874-178">Le recomendamos que revierta siempre la aserción cuando acabe de usarla.</span><span class="sxs-lookup"><span data-stu-id="92874-178">It is good practice to always revert the assert when you have finished using it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92874-179">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="92874-179">Example</span></span>  
 <span data-ttu-id="92874-180">En el ejemplo siguiente se implementa el procedimiento de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="92874-180">The following example implements the procedure in the previous section.</span></span> <span data-ttu-id="92874-181">En el ejemplo, un proyecto denominado `Sandboxer` en una solución de Visual Studio también contiene un proyecto denominado `UntrustedCode` que implementa la clase `UntrustedClass`.</span><span class="sxs-lookup"><span data-stu-id="92874-181">In the example, a project named `Sandboxer` in a Visual Studio solution also contains a project named `UntrustedCode`, which implements the class `UntrustedClass`.</span></span> <span data-ttu-id="92874-182">En este escenario se supone que ha descargado un ensamblado de biblioteca que contiene un método que debe devolver `true` o `false` para indicar si el número proporcionado es un número de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="92874-182">This scenario assumes that you have downloaded a library assembly containing a method that is expected to return `true` or `false` to indicate whether the number you provided is a Fibonacci number.</span></span> <span data-ttu-id="92874-183">En su lugar, el método intenta leer un archivo de su equipo.</span><span class="sxs-lookup"><span data-stu-id="92874-183">Instead, the method attempts to read a file from your computer.</span></span> <span data-ttu-id="92874-184">En el ejemplo siguiente se muestra el código no confiable.</span><span class="sxs-lookup"><span data-stu-id="92874-184">The following example shows the untrusted code.</span></span>  
  
```csharp
using System;  
using System.IO;  
namespace UntrustedCode  
{  
    public class UntrustedClass  
    {  
        // Pretend to be a method checking if a number is a Fibonacci  
        // but which actually attempts to read a file.  
        public static bool IsFibonacci(int number)  
        {  
           File.ReadAllText("C:\\Temp\\file.txt");  
           return false;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="92874-185">En el ejemplo siguiente se muestra el código de la aplicación `Sandboxer` que ejecuta el código no confiable.</span><span class="sxs-lookup"><span data-stu-id="92874-185">The following example shows the `Sandboxer` application code that executes the untrusted code.</span></span>  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Security;  
using System.Security.Policy;  
using System.Security.Permissions;  
using System.Reflection;  
using System.Runtime.Remoting;  
  
//The Sandboxer class needs to derive from MarshalByRefObject so that we can create it in another
// AppDomain and refer to it from the default AppDomain.  
class Sandboxer : MarshalByRefObject  
{  
    const string pathToUntrusted = @"..\..\..\UntrustedCode\bin\Debug";  
    const string untrustedAssembly = "UntrustedCode";  
    const string untrustedClass = "UntrustedCode.UntrustedClass";  
    const string entryPoint = "IsFibonacci";  
    private static Object[] parameters = { 45 };  
    static void Main()  
    {  
        //Setting the AppDomainSetup. It is very important to set the ApplicationBase to a folder
        //other than the one in which the sandboxer resides.  
        AppDomainSetup adSetup = new AppDomainSetup();  
        adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
  
        //Setting the permissions for the AppDomain. We give the permission to execute and to
        //read/discover the location where the untrusted code is loaded.  
        PermissionSet permSet = new PermissionSet(PermissionState.None);  
        permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
  
        //We want the sandboxer assembly's strong name, so that we can add it to the full trust list.  
        StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
  
        //Now we have everything we need to create the AppDomain, so let's create it.  
        AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
  
        //Use CreateInstanceFrom to load an instance of the Sandboxer class into the  
        //new AppDomain.
        ObjectHandle handle = Activator.CreateInstanceFrom(  
            newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
            typeof(Sandboxer).FullName  
            );  
        //Unwrap the new domain instance into a reference in this domain and use it to execute the
        //untrusted code.  
        Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
        newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    }  
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new Assembly. This might be a method you know, or
        //you can use Assembly.EntryPoint to get to the main function in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            //Now invoke the method.  
            bool retVal = (bool)target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
            // When we print informations from a SecurityException extra information can be printed if we are
            //calling it with a full-trust stack.  
            new PermissionSet(PermissionState.Unrestricted).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="92874-186">Consulte también</span><span class="sxs-lookup"><span data-stu-id="92874-186">See also</span></span>

- [<span data-ttu-id="92874-187">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="92874-187">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
