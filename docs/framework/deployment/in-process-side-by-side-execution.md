---
title: Ejecución en paralelo y en proceso
ms.date: 03/30/2017
helpviewer_keywords:
- in-process side-by-side execution
- side-by-side execution, in-process
ms.assetid: 18019342-a810-4986-8ec2-b933a17c2267
ms.openlocfilehash: 0c699f90143a87b7e7bee24c892efe2936a9399e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716479"
---
# <a name="in-process-side-by-side-execution"></a>Ejecución en paralelo y en proceso
A partir de .NET Framework 4, puede usar el hospedaje en paralelo en el mismo proceso para ejecutar varias versiones de Common Language Runtime (CLR) en un único proceso. De forma predeterminada, los componentes COM administrados se ejecutan con la versión de .NET Framework con la que se han compilado, independientemente de la versión de .NET Framework que se haya cargado para el proceso.  
  
## <a name="background"></a>Fondo  
 .NET Framework siempre ha proporcionado hospedaje en paralelo para aplicaciones de código administrado, pero antes de .NET Framework 4, no proporcionaba esta funcionalidad para los componentes COM administrados. Anteriormente, los componentes COM administrados que se cargaban en un proceso se ejecutaban con la versión del tiempo de ejecución que ya se había cargado o con la última versión instalada de .NET Framework. Si esta versión no era compatible con el componente COM, se producía un error en el componente.  
  
 .NET Framework 4 proporciona un enfoque nuevo para el hospedaje en paralelo que garantiza lo siguiente:  
  
- La instalación de una nueva versión de .NET Framework no afecta a las aplicaciones existentes.  
  
- Las aplicaciones se ejecutan con la versión de .NET Framework con la que se compilaron. No usan la nueva versión de .NET Framework a menos que se les indique expresamente que lo hagan. Aun así, es más fácil que las aplicaciones pasen a usar una nueva versión de .NET Framework.  
  
## <a name="effects-on-users-and-developers"></a>Consecuencias para los usuarios y los desarrolladores  
  
- **Usuarios finales y administradores del sistema**. Estos usuarios ahora pueden estar más seguros de que la instalación de una nueva versión del tiempo de ejecución, ya sea de forma independiente o con una aplicación, no afectará a sus equipos. Las aplicaciones existentes seguirán ejecutándose como antes.  
  
- **Desarrolladores de aplicaciones**. El hospedaje en paralelo prácticamente no afecta a los desarrolladores de aplicaciones. De forma predeterminada, las aplicaciones siempre se ejecutan en la versión de .NET Framework en la que se han compilado; esto no ha cambiado. Aun así, los desarrolladores pueden invalidar este comportamiento e indicarle a la aplicación que se ejecute en una versión más reciente de .NET Framework (vea el [escenario 2](#scenarios)).  
  
- **Desarrolladores de bibliotecas y consumidores**. El hospedaje en paralelo no resuelve los problemas de compatibilidad a los que se enfrentan los desarrolladores de bibliotecas. Una biblioteca cargada directamente por una aplicación, ya sea a través de una referencia directa o de una llamada a <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>, sigue usando el tiempo de ejecución del <xref:System.AppDomain> en el que se carga. Debe probar las bibliotecas con todas las versiones de .NET Framework que quiera admitir. Si una aplicación se compila con el entorno de ejecución de .NET Framework 4, pero incluye una biblioteca compilada con otro anterior, la biblioteca también usará el entorno de ejecución de .NET Framework 4. Sin embargo, si se tiene una aplicación compilada con un entorno de ejecución anterior y una biblioteca compilada con .NET Framework 4, se debe forzar a que la aplicación también use .NET Framework 4 (consulte el [escenario 3](#scenarios)).  
  
- **Desarrolladores de componentes COM administrados**. Antes, los componentes COM administrados se ejecutaban automáticamente con la versión más reciente del tiempo de ejecución instalada en el equipo. Ahora puede ejecutar los componentes COM con la versión del tiempo de ejecución en la que se han compilado.  
  
     Como se muestra en la tabla siguiente, los componentes compilados con .NET Framework versión 1.1 pueden ejecutarse en paralelo con componentes de la versión 4, pero no pueden ejecutarse con componentes de las versiones 2.0, 3.0 o 3.5, ya que el hospedaje en paralelo no está disponible para estas versiones.  
  
    |Versión de .NET Framework|1.1|2.0 - 3.5|4|  
    |----------------------------|---------|----------------|-------|  
    |1.1|No es aplicable|No|Sí|  
    |2.0 - 3.5|No|No es aplicable|Sí|  
    |4|Sí|Sí|No es aplicable|  
  
> [!NOTE]
> Las versiones 3.0 y 3.5 de .NET Framework se compilan de forma incremental en la versión 2.0 y no es necesario ejecutarlas en paralelo. Se trata básicamente de la misma versión.  
  
<a name="scenarios"></a>   
## <a name="common-side-by-side-hosting-scenarios"></a>Escenarios comunes de hospedaje en paralelo  
  
- **Escenario 1:** aplicación nativa en la que se usan componentes COM compilados con versiones anteriores de .NET Framework.  
  
     Versiones de .NET Framework instaladas: .NET Framework 4 y todas las demás versiones de .NET Framework que usan los componentes COM.  
  
     Qué se debe hacer: en este escenario, no haga nada. Los componentes COM se ejecutarán con la versión de .NET Framework con la que se han registrado.  
  
- **Escenario 2**: aplicación administrada compilada con .NET Framework 2.0  SP1 que preferiblemente debería ejecutarse con .NET Framework 2.0, pero que se puede ejecutar en .NET Framework 2.0 si la versión 4 no está presente.  
  
     Versiones de .NET Framework instaladas: Versión anterior de .NET Framework y .NET Framework 4.  
  
     Qué se debe hacer: en el [archivo de configuración de la aplicación](../configure-apps/index.md) que está en el directorio de la aplicación, use el [elemento \<startup>](../configure-apps/file-schema/startup/startup-element.md) y el [elemento \<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) establecidos de esta forma:  
  
    ```xml  
    <configuration>  
      <startup >  
        <supportedRuntime version="v2.0.50727" />  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
- **Escenario 3:** aplicación nativa que usa componentes COM compilados con versiones anteriores de .NET Framework que quiere ejecutar con .NET Framework 4.  
  
     Versiones de .NET Framework instaladas: .NET Framework 4.  
  
     Qué se debe hacer: en el archivo de configuración de la aplicación en el directorio de la aplicación, use el elemento `<startup>` con el atributo `useLegacyV2RuntimeActivationPolicy` establecido en `true` y el elemento `<supportedRuntime>` establecido de esta forma:  
  
    ```xml  
    <configuration>  
      <startup useLegacyV2RuntimeActivationPolicy="true">  
        <supportedRuntime version="v4.0" />  
      </startup>  
    </configuration>  
    ```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un host COM no administrado que está ejecutando un componente COM administrado mediante la versión de .NET Framework que el componente debe usar de acuerdo con su compilación.  
  
 Para ejecutar el ejemplo que se muestra a continuación, compile y registre el siguiente componente COM administrado con .NET Framework 3.5. Para registrar el componente, en el menú **Proyecto**, haga clic en **Propiedades**, en la pestaña **Compilar** y, después, active la casilla **Registrar para interoperabilidad COM**.  
  
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
  
 Compile la siguiente aplicación de C++ no administrada, que activa el objeto COM que se crea en el ejemplo anterior.  
  
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
  
## <a name="see-also"></a>Vea también

- [Elemento \<startup>](../configure-apps/file-schema/startup/startup-element.md)
- [\<supportedRuntime > Elemento](../configure-apps/file-schema/startup/supportedruntime-element.md)
