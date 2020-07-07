---
title: Ejecución en paralelo y en proceso
description: Use el hospedaje en paralelo en el mismo proceso para ejecutar varias versiones de Common Language Runtime (CLR) en un único proceso .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
ms.openlocfilehash: 078f2eaada8fac57138bef22d46218ef2ccda835
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622606"
---
# <a name="in-process-side-by-side-execution"></a><span data-ttu-id="ebb74-103">Ejecución en paralelo y en proceso</span><span class="sxs-lookup"><span data-stu-id="ebb74-103">In-Process Side-by-Side Execution</span></span>
<span data-ttu-id="ebb74-104">A partir de .NET Framework 4, puede usar el hospedaje en paralelo en el mismo proceso para ejecutar varias versiones de Common Language Runtime (CLR) en un único proceso.</span><span class="sxs-lookup"><span data-stu-id="ebb74-104">Starting with the .NET Framework 4, you can use in-process side-by-side hosting to run multiple versions of the common language runtime (CLR) in a single process.</span></span> <span data-ttu-id="ebb74-105">De forma predeterminada, los componentes COM administrados se ejecutan con la versión de .NET Framework con la que se han compilado, independientemente de la versión de .NET Framework que se haya cargado para el proceso.</span><span class="sxs-lookup"><span data-stu-id="ebb74-105">By default, managed COM components run with the .NET Framework version they were built with, regardless of the .NET Framework version that is loaded for the process.</span></span>  
  
## <a name="background"></a><span data-ttu-id="ebb74-106">Fondo</span><span class="sxs-lookup"><span data-stu-id="ebb74-106">Background</span></span>  
 <span data-ttu-id="ebb74-107">.NET Framework siempre ha proporcionado hospedaje en paralelo para aplicaciones de código administrado, pero antes de .NET Framework 4, no proporcionaba esta funcionalidad para los componentes COM administrados.</span><span class="sxs-lookup"><span data-stu-id="ebb74-107">The .NET Framework has always provided side-by-side hosting for managed code applications, but before the .NET Framework 4, it did not provide that functionality for managed COM components.</span></span> <span data-ttu-id="ebb74-108">Anteriormente, los componentes COM administrados que se cargaban en un proceso se ejecutaban con la versión del tiempo de ejecución que ya se había cargado o con la última versión instalada de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ebb74-108">In the past, managed COM components that were loaded into a process ran either with the version of the runtime that was already loaded or with the latest installed version of the .NET Framework.</span></span> <span data-ttu-id="ebb74-109">Si esta versión no era compatible con el componente COM, se producía un error en el componente.</span><span class="sxs-lookup"><span data-stu-id="ebb74-109">If this version was not compatible with the COM component, the component would fail.</span></span>  
  
 <span data-ttu-id="ebb74-110">.NET Framework 4 proporciona un enfoque nuevo para el hospedaje en paralelo que garantiza lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebb74-110">The .NET Framework 4 provides a new approach to side-by-side hosting that ensures the following:</span></span>  
  
- <span data-ttu-id="ebb74-111">La instalación de una nueva versión de .NET Framework no afecta a las aplicaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="ebb74-111">Installing a new version of the .NET Framework has no effect on existing applications.</span></span>  
  
- <span data-ttu-id="ebb74-112">Las aplicaciones se ejecutan con la versión de .NET Framework con la que se compilaron.</span><span class="sxs-lookup"><span data-stu-id="ebb74-112">Applications run against the version of the .NET Framework that they were built with.</span></span> <span data-ttu-id="ebb74-113">No usan la nueva versión de .NET Framework a menos que se les indique expresamente que lo hagan.</span><span class="sxs-lookup"><span data-stu-id="ebb74-113">They do not use the new version of the .NET Framework unless expressly directed to do so.</span></span> <span data-ttu-id="ebb74-114">Aun así, es más fácil que las aplicaciones pasen a usar una nueva versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ebb74-114">However, it is easier for applications to transition to using a new version of the .NET Framework.</span></span>  
  
## <a name="effects-on-users-and-developers"></a><span data-ttu-id="ebb74-115">Consecuencias para los usuarios y los desarrolladores</span><span class="sxs-lookup"><span data-stu-id="ebb74-115">Effects on Users and Developers</span></span>  
  
- <span data-ttu-id="ebb74-116">**Usuarios finales y administradores del sistema**.</span><span class="sxs-lookup"><span data-stu-id="ebb74-116">**End users and system administrators**.</span></span> <span data-ttu-id="ebb74-117">Estos usuarios ahora pueden estar más seguros de que la instalación de una nueva versión del tiempo de ejecución, ya sea de forma independiente o con una aplicación, no afectará a sus equipos.</span><span class="sxs-lookup"><span data-stu-id="ebb74-117">These users can now have greater confidence that when they install a new version of the runtime, either independently or with an application, it will have no impact on their computers.</span></span> <span data-ttu-id="ebb74-118">Las aplicaciones existentes seguirán ejecutándose como antes.</span><span class="sxs-lookup"><span data-stu-id="ebb74-118">Existing applications will continue to run as they did before.</span></span>  
  
- <span data-ttu-id="ebb74-119">**Desarrolladores de aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="ebb74-119">**Application developers**.</span></span> <span data-ttu-id="ebb74-120">El hospedaje en paralelo prácticamente no afecta a los desarrolladores de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ebb74-120">Side-by-side hosting has almost no effect on application developers.</span></span> <span data-ttu-id="ebb74-121">De forma predeterminada, las aplicaciones siempre se ejecutan en la versión de .NET Framework en la que se han compilado; esto no ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="ebb74-121">By default, applications always run against the version of the .NET Framework they were built on; this has not changed.</span></span> <span data-ttu-id="ebb74-122">Aun así, los desarrolladores pueden invalidar este comportamiento e indicarle a la aplicación que se ejecute en una versión más reciente de .NET Framework (vea el [escenario 2](#scenarios)).</span><span class="sxs-lookup"><span data-stu-id="ebb74-122">However, developers can override this behavior and direct the application to run under a newer version of the .NET Framework (see [scenario 2](#scenarios)).</span></span>  
  
- <span data-ttu-id="ebb74-123">**Desarrolladores de bibliotecas y consumidores**.</span><span class="sxs-lookup"><span data-stu-id="ebb74-123">**Library developers and consumers**.</span></span> <span data-ttu-id="ebb74-124">El hospedaje en paralelo no resuelve los problemas de compatibilidad a los que se enfrentan los desarrolladores de bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="ebb74-124">Side-by-side hosting does not solve the compatibility problems that library developers face.</span></span> <span data-ttu-id="ebb74-125">Una biblioteca cargada directamente por una aplicación, ya sea a través de una referencia directa o de una llamada a <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, sigue usando el tiempo de ejecución del <xref:System.AppDomain> en el que se carga.</span><span class="sxs-lookup"><span data-stu-id="ebb74-125">A library that is directly loaded by an application -- either through a direct reference or through an <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> call -- continues to use the runtime of the <xref:System.AppDomain> it is loaded into.</span></span> <span data-ttu-id="ebb74-126">Debe probar las bibliotecas con todas las versiones de .NET Framework que quiera admitir.</span><span class="sxs-lookup"><span data-stu-id="ebb74-126">You should test your libraries against all versions of the .NET Framework that you want to support.</span></span> <span data-ttu-id="ebb74-127">Si una aplicación se compila con el entorno de ejecución de .NET Framework 4, pero incluye una biblioteca compilada con otro anterior, la biblioteca también usará el entorno de ejecución de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ebb74-127">If an application is compiled using the .NET Framework 4 runtime but includes a library that was built using an earlier runtime, that library will use the .NET Framework 4 runtime as well.</span></span> <span data-ttu-id="ebb74-128">Sin embargo, si se tiene una aplicación compilada con un entorno de ejecución anterior y una biblioteca compilada con .NET Framework 4, se debe forzar a que la aplicación también use .NET Framework 4 (consulte el [escenario 3](#scenarios)).</span><span class="sxs-lookup"><span data-stu-id="ebb74-128">However, if you have an application that was built using an earlier runtime and a library that was built using the .NET Framework 4, you must force your application to also use the .NET Framework 4 (see [scenario 3](#scenarios)).</span></span>  
  
- <span data-ttu-id="ebb74-129">**Desarrolladores de componentes COM administrados**.</span><span class="sxs-lookup"><span data-stu-id="ebb74-129">**Managed COM component developers**.</span></span> <span data-ttu-id="ebb74-130">Antes, los componentes COM administrados se ejecutaban automáticamente con la versión más reciente del tiempo de ejecución instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="ebb74-130">In the past, managed COM components automatically ran using the latest version of the runtime installed on the computer.</span></span> <span data-ttu-id="ebb74-131">Ahora puede ejecutar los componentes COM con la versión del tiempo de ejecución en la que se han compilado.</span><span class="sxs-lookup"><span data-stu-id="ebb74-131">You can now execute COM components against the version of the runtime they were built with.</span></span>  
  
     <span data-ttu-id="ebb74-132">Como se muestra en la tabla siguiente, los componentes compilados con .NET Framework versión 1.1 pueden ejecutarse en paralelo con componentes de la versión 4, pero no pueden ejecutarse con componentes de las versiones 2.0, 3.0 o 3.5, ya que el hospedaje en paralelo no está disponible para estas versiones.</span><span class="sxs-lookup"><span data-stu-id="ebb74-132">As shown by the following table, components that were built with the .NET Framework version 1.1 can run side by side with version 4 components, but they cannot run with version 2.0, 3.0, or 3.5 components, because side-by-side hosting is not available for those versions.</span></span>  
  
    |<span data-ttu-id="ebb74-133">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ebb74-133">.NET Framework version</span></span>|<span data-ttu-id="ebb74-134">1.1</span><span class="sxs-lookup"><span data-stu-id="ebb74-134">1.1</span></span>|<span data-ttu-id="ebb74-135">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="ebb74-135">2.0 - 3.5</span></span>|<span data-ttu-id="ebb74-136">4</span><span class="sxs-lookup"><span data-stu-id="ebb74-136">4</span></span>|  
    |----------------------------|---------|----------------|-------|  
    |<span data-ttu-id="ebb74-137">1.1</span><span class="sxs-lookup"><span data-stu-id="ebb74-137">1.1</span></span>|<span data-ttu-id="ebb74-138">No es aplicable</span><span class="sxs-lookup"><span data-stu-id="ebb74-138">Not applicable</span></span>|<span data-ttu-id="ebb74-139">No</span><span class="sxs-lookup"><span data-stu-id="ebb74-139">No</span></span>|<span data-ttu-id="ebb74-140">Sí</span><span class="sxs-lookup"><span data-stu-id="ebb74-140">Yes</span></span>|  
    |<span data-ttu-id="ebb74-141">2.0 - 3.5</span><span class="sxs-lookup"><span data-stu-id="ebb74-141">2.0 - 3.5</span></span>|<span data-ttu-id="ebb74-142">No</span><span class="sxs-lookup"><span data-stu-id="ebb74-142">No</span></span>|<span data-ttu-id="ebb74-143">No es aplicable</span><span class="sxs-lookup"><span data-stu-id="ebb74-143">Not applicable</span></span>|<span data-ttu-id="ebb74-144">Sí</span><span class="sxs-lookup"><span data-stu-id="ebb74-144">Yes</span></span>|  
    |<span data-ttu-id="ebb74-145">4</span><span class="sxs-lookup"><span data-stu-id="ebb74-145">4</span></span>|<span data-ttu-id="ebb74-146">Sí</span><span class="sxs-lookup"><span data-stu-id="ebb74-146">Yes</span></span>|<span data-ttu-id="ebb74-147">Sí</span><span class="sxs-lookup"><span data-stu-id="ebb74-147">Yes</span></span>|<span data-ttu-id="ebb74-148">No es aplicable</span><span class="sxs-lookup"><span data-stu-id="ebb74-148">Not applicable</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="ebb74-149">Las versiones 3.0 y 3.5 de .NET Framework se compilan de forma incremental en la versión 2.0 y no es necesario ejecutarlas en paralelo.</span><span class="sxs-lookup"><span data-stu-id="ebb74-149">.NET Framework versions 3.0 and 3.5 are built incrementally on version 2.0, and do not need to run side by side.</span></span> <span data-ttu-id="ebb74-150">Se trata básicamente de la misma versión.</span><span class="sxs-lookup"><span data-stu-id="ebb74-150">These are inherently the same version.</span></span>  
  
<a name="scenarios"></a>
## <a name="common-side-by-side-hosting-scenarios"></a><span data-ttu-id="ebb74-151">Escenarios comunes de hospedaje en paralelo</span><span class="sxs-lookup"><span data-stu-id="ebb74-151">Common Side-by-Side Hosting Scenarios</span></span>  
  
- <span data-ttu-id="ebb74-152">**Escenario 1:** aplicación nativa en la que se usan componentes COM compilados con versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ebb74-152">**Scenario 1:** Native application that uses COM components built with earlier versions of the .NET Framework.</span></span>  
  
     <span data-ttu-id="ebb74-153">Versiones de .NET Framework instaladas: .NET Framework 4 y todas las demás versiones de .NET Framework que usan los componentes COM.</span><span class="sxs-lookup"><span data-stu-id="ebb74-153">.NET Framework versions installed: The .NET Framework 4 and all other versions of the .NET Framework used by the COM components.</span></span>  
  
     <span data-ttu-id="ebb74-154">Qué se debe hacer: en este escenario, no haga nada.</span><span class="sxs-lookup"><span data-stu-id="ebb74-154">What to do: In this scenario, do nothing.</span></span> <span data-ttu-id="ebb74-155">Los componentes COM se ejecutarán con la versión de .NET Framework con la que se han registrado.</span><span class="sxs-lookup"><span data-stu-id="ebb74-155">The COM components will run with the version of the .NET Framework they were registered with.</span></span>  
  
- <span data-ttu-id="ebb74-156">**Escenario 2**: aplicación administrada compilada con .NET Framework 2.0  SP1 que preferiblemente debería ejecutarse con .NET Framework 2.0, pero que se puede ejecutar en .NET Framework 2.0 si la versión 4 no está presente.</span><span class="sxs-lookup"><span data-stu-id="ebb74-156">**Scenario 2**: Managed application built with the .NET Framework 2.0 SP1 that you would prefer to run with the .NET Framework 2.0, but are willing to run on the .NET Framework 4 if version 2.0 is not present.</span></span>  
  
     <span data-ttu-id="ebb74-157">Versiones de .NET Framework instaladas: Versión anterior de .NET Framework y .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ebb74-157">.NET Framework versions installed: An earlier version of the .NET Framework and the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="ebb74-158">Qué se debe hacer: En el [archivo de configuración de la aplicación](../configure-apps/index.md) en el directorio de la aplicación, use el elemento [\<startup> ](../configure-apps/file-schema/startup/startup-element.md) y el elemento [\<supportedRuntime> ](../configure-apps/file-schema/startup/supportedruntime-element.md) establecido de esta forma:</span><span class="sxs-lookup"><span data-stu-id="ebb74-158">What to do: In the [application configuration file](../configure-apps/index.md) in the application directory, use the [\<startup> element](../configure-apps/file-schema/startup/startup-element.md) and the [\<supportedRuntime> element](../configure-apps/file-schema/startup/supportedruntime-element.md) set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
- <span data-ttu-id="ebb74-159">**Escenario 3:** aplicación nativa que usa componentes COM compilados con versiones anteriores de .NET Framework que quiere ejecutar con .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ebb74-159">**Scenario 3:** Native application that uses COM components built with earlier versions of the .NET Framework that you want to run with the .NET Framework 4.</span></span>  
  
     <span data-ttu-id="ebb74-160">Versiones de .NET Framework instaladas: .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ebb74-160">.NET Framework versions installed: The .NET Framework 4.</span></span>  
  
     <span data-ttu-id="ebb74-161">Qué se debe hacer: en el archivo de configuración de la aplicación en el directorio de la aplicación, use el elemento `<startup>` con el atributo `useLegacyV2RuntimeActivationPolicy` establecido en `true` y el elemento `<supportedRuntime>` establecido de esta forma:</span><span class="sxs-lookup"><span data-stu-id="ebb74-161">What to do: In the application configuration file in the application directory, use the `<startup>` element with the `useLegacyV2RuntimeActivationPolicy` attribute set to `true` and the `<supportedRuntime>` element set as follows:</span></span>  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a><span data-ttu-id="ebb74-162">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ebb74-162">Example</span></span>  
 <span data-ttu-id="ebb74-163">En el ejemplo siguiente se muestra un host COM no administrado que está ejecutando un componente COM administrado mediante la versión de .NET Framework que el componente debe usar de acuerdo con su compilación.</span><span class="sxs-lookup"><span data-stu-id="ebb74-163">The following example demonstrates an unmanaged COM host that is running a managed COM component by using the version of the .NET Framework that the component was compiled to use.</span></span>  
  
 <span data-ttu-id="ebb74-164">Para ejecutar el ejemplo que se muestra a continuación, compile y registre el siguiente componente COM administrado con .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="ebb74-164">To run the following example, compile and register the following managed COM component using the .NET Framework 3.5.</span></span> <span data-ttu-id="ebb74-165">Para registrar el componente, en el menú **Proyecto**, haga clic en **Propiedades**, en la pestaña **Compilar** y, después, active la casilla **Registrar para interoperabilidad COM**.</span><span class="sxs-lookup"><span data-stu-id="ebb74-165">To register the component, on the **Project** menu, click **Properties**, click the **Build** tab, and then select the **Register for COM interop** check box.</span></span>  
  
```csharp
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Runtime.InteropServices;  
  
namespace BasicComObject  
{  
    [ComVisible(true), Guid("9C99C4B5-CA54-4c58-8988-49B6811BA53B")]  
    public class MyObject : SimpleObjectModel.IPrintInfo  
    {  
        public MyObject()  
        {  
        }  
        public void PrintInfo()  
        {  
            Console.WriteLine("MyObject was activated in {0} runtime in:\n\tAppDomain {1}:{2}", System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion(), AppDomain.CurrentDomain.Id, AppDomain.CurrentDomain.FriendlyName);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="ebb74-166">Compile la siguiente aplicación de C++ no administrada, que activa el objeto COM que se crea en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="ebb74-166">Compile the following unmanaged C++ application, which activates the COM object that is created by the previous example.</span></span>  
  
```cpp
#include "stdafx.h"  
#include <string>  
#include <iostream>  
#include <objbase.h>  
#include <string.h>  
#include <process.h>  
  
using namespace std;  
  
int _tmain(int argc, _TCHAR* argv[])  
{  
    char input;  
    CoInitialize(NULL) ;  
    CLSID clsid;  
    HRESULT hr;  
    HRESULT clsidhr = CLSIDFromString(L"{9C99C4B5-CA54-4c58-8988-49B6811BA53B}",&clsid);  
    hr = -1;  
    if (FAILED(clsidhr))  
    {  
        printf("Failed to construct CLSID from String\n");  
    }  
    UUID id = __uuidof(IUnknown);  
    IUnknown * pUnk = NULL;  
    hr = ::CoCreateInstance(clsid,NULL,CLSCTX_INPROC_SERVER,id,(void **) &pUnk);  
    if (FAILED(hr))  
    {  
        printf("Failed CoCreateInstance\n");  
    }else  
    {  
        pUnk->AddRef();  
        printf("Succeeded\n");  
    }  
  
    DISPID dispid;  
    IDispatch* pPrintInfo;  
    pUnk->QueryInterface(IID_IDispatch, (void**)&pPrintInfo);  
    OLECHAR FAR* szMethod[1];  
    szMethod[0]=OLESTR("PrintInfo");
    hr = pPrintInfo->GetIDsOfNames(IID_NULL,szMethod, 1, LOCALE_SYSTEM_DEFAULT, &dispid);  
    DISPPARAMS dispparams;  
    dispparams.cNamedArgs = 0;  
    dispparams.cArgs = 0;  
    VARIANTARG* pvarg = NULL;  
    EXCEPINFO * pexcepinfo = NULL;  
    WORD wFlags = DISPATCH_METHOD ;  
;  
    LPVARIANT pvRet = NULL;  
    UINT * pnArgErr = NULL;  
    hr = pPrintInfo->Invoke(dispid,IID_NULL, LOCALE_USER_DEFAULT, wFlags,  
        &dispparams, pvRet, pexcepinfo, pnArgErr);  
    printf("Press Enter to exit");  
    scanf_s("%c",&input);  
    CoUninitialize();  
    return 0;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebb74-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebb74-167">See also</span></span>

- [<span data-ttu-id="ebb74-168">Elemento \<startup></span><span class="sxs-lookup"><span data-stu-id="ebb74-168">\<startup> Element</span></span>](../configure-apps/file-schema/startup/startup-element.md)
- [<span data-ttu-id="ebb74-169">Elemento \<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="ebb74-169">\<supportedRuntime> Element</span></span>](../configure-apps/file-schema/startup/supportedruntime-element.md)
